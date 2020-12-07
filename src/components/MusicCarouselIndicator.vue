<template>
  <div class="music-indicator">
    <div
      v-for="(music, index) in musicData"
      :key="index"
      :class="`music-indicator-item`"
      :style="transitionData[index]"
      @mouseover="chooseMusic(index)"
    >
      <img :src="music.imgUrl" />
    </div>
  </div>
</template>

<script>
export default {
  name: "music-carousel-indicator",
  data() {
    return {
      // Transition css of each element
      transitionData: Array.apply(null, Array(this.musicData.length)).map(
        (x, i) => {
          return {
            transition: `${(i + 1) * 0.15}s`,
          };
        }
      ),
    };
  },
  props: {
    musicData: Array,
  },
  methods: {
    chooseMusic(index) {
      this.$emit("setSlide", index);
    },
  },
};
</script>

<style>
.music-indicator {
  position: absolute;
  bottom: -100px;
  right: 10px;
}

.music-indicator-item {
  display: inline-block;
  width: 70px;
  height: 70px;
  margin-right: 5px;
  visibility: hidden;
  box-shadow: 0px 3px 10px rgba(255, 255, 255, 0.8);
}

.music-indicator-item:hover img {
  border: 5px solid #fff;
}

.music-indicator-item img {
  width: 70px;
  height: 70px;
  border-radius: 5px;
  transition: 0.1s;
  object-fit: cover;
}

.music-carousel:hover .music-indicator-item {
  visibility: unset;
  transform: translateY(-110px);
}
</style>
