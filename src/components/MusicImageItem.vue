<template>
  <div
    class="music-item-img"
    :class="rounded ? 'rounded-circle' : ''"
    :style="{ width, height }"
  >
    <img :src="imgUrl" :style="{width:'100%', height}"/>
    <div
      v-if="fullOpt === 3"
      class="music-item-control"
      :style="{ background: `rgba(0,0,0,${opacity})` }"
    >
      <i class="far fa-heart fa-2x"></i>
      <router-link to="/album/">
        <i class="far fa-play-circle fa-4x"></i>
      </router-link>
      <i class="fas fa-ellipsis-h fa-2x"></i>
    </div>
    <div
      v-else-if="fullOpt === 1"
      class="music-item-control"
      :style="{ background: `rgba(0,0,0,${opacity})` }"
    >
      <i class="far fa-play-circle fa-3x"></i>
    </div>
  </div>
</template>

<script>
export default {
  name: "music-image-item",
  props: {
    imgUrl: {
      type: String,
      required: true,
    },
    rounded: {
      type: Boolean,
      default: false,
    },
    opacity: {
      type: Number,
      default: 0.6,
    },
    fullOpt: {
      type: Number,
      default: 3,
    },
    width: {
      type: String,
      default: "100%",
    },
    height: {
      type: String,
    },
  },
};
</script>

<style>
.music-item-img {
  position: relative;
  width: 100%;
  cursor: pointer;
  overflow: hidden;
  border-radius: 5px;
}

.music-item-img:hover .music-item-control {
  visibility: unset;
}

.music-item-img:hover img {
  transform: scale(1.1, 1.1);
}

.music-item-img img {
  width: 100%;
  /* border-radius: 5px; */
  transition: 0.25s;
}

.music-item-control {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  display: flex;
  border-radius: 5px;
  align-items: center;
  justify-content: space-around;
  visibility: hidden;
}

.music-item-control i {
  color: #fff;
  padding: 5px;
  border-radius: 50%;
  cursor: pointer;
}
.music-item-control .fa-2x:hover {
  background: #888;
}
</style>
