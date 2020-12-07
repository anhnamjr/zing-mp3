<template>
  <div class="music-list mb-5">
    <div class="music-list-title mb-3">
      <span>{{ title }}</span>
      <div v-if="controls" class="music-list-controls">
        <i
          class="fas fa-chevron-left"
          :class="currentSlide === 1 ? 'controls-disable' : ''"
          @click="prevSlide"
        ></i>
        <i
          class="fas fa-chevron-right"
          :class="currentSlide === numSlide ? 'controls-disable' : ''"
          @click="nextSlide"
        ></i>
      </div>
    </div>
    <b-carousel :interval="interval" ref="myCarousel">
      <b-carousel-slide v-for="slide in numSlide" :key="slide">
        <template v-slot:img>
          <b-row
            v-if="
              musicList.slice((slide - 1) * numItem, slide * numItem).length ===
                numItem
            "
          >
            <music-item
              v-for="item in musicList.slice(
                (slide - 1) * numItem,
                slide * numItem
              )"
              :key="item.id"
              :imgUrl="item.imgUrl"
              :title="item.title"
            />
          </b-row>
          <b-row v-else>
            <music-item
              v-for="item in musicList.slice(
                (slide - 1) * numItem,
                slide * numItem
              )"
              :key="item.id"
              :imgUrl="item.imgUrl"
              :title="item.title"
            />
            <b-col
              v-for="remainNum in Math.abs(
                musicList.slice((slide - 1) * numItem, slide * numItem).length -
                  numItem
              )"
              :key="remainNum"
            ></b-col>
          </b-row>
        </template>
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
import MusicItem from "@/components/MusicItem";
export default {
  name: "music-list",
  props: {
    title: {
      type: String,
      required: true,
    },
    musicList: {
      type: Array,
      required: true,
    },
    numItem: {
      type: Number,
    },
    interval: {
      type: Number,
      default: 0
    }, 
    controls: {
      type: Boolean,
      default: true
    }
  },
  components: {
    MusicItem,
  },
  data() {
    return {
      currentSlide: 1,
    };
  },
  computed: {
    numSlide: function() {
      return Math.ceil(this.musicList.length / this.numItem);
    },
  },
  methods: {
    nextSlide() {
      if (this.currentSlide < this.numSlide) {
        this.$refs.myCarousel.next();
        this.currentSlide++;
      }
    },

    prevSlide() {
      if (this.currentSlide > 1) {
        this.$refs.myCarousel.prev();
        this.currentSlide--;
      }
    },
  },
};
</script>

<style>
.music-list-title {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.music-list-title span {
  font-size: 1.8rem;
  font-weight: 700;
  text-transform: capitalize;
}

.music-list-controls {
  font-size: 1.8rem;
}

.music-list-controls i:first-child {
  margin-right: 20px;
}

.music-list-controls i {
  cursor: pointer;
}

.music-list-controls i:hover {
  color: #6e55b4;
}

.controls-disable {
  cursor: not-allowed !important;
  color: #ddd;
}

.controls-disable:hover {
  color: #ddd !important;
}
</style>
