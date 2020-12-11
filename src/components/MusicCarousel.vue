<template>
  <b-container class="p-0 music-carousel">
    <b-carousel
      img-height="480px"
      img-width="100%"
      :interval="5000"
      ref="nameCarousel"
    >
      <b-carousel-slide
        v-for="(music, index) in musicData"
        :key="index"
        :img-src="music.imgUrl"
      ></b-carousel-slide>
    </b-carousel>
    <music-carousel-indicator :musicData="musicData" @setSlide="setSlide"/>
  </b-container>
</template>

<script>
import MusicCarouselIndicator from "@/components/MusicCarouselIndicator"
export default {
  name: "music-carousel",
  components: {MusicCarouselIndicator},
  props: {
    musicData: Array, nameCarousel: String
  },
  data(){
    return {
      indexSlide: null,
      slideMove: null
    }
  },
  methods: {
    setSlide(index){
      this.indexSlide = index
      this.$refs.nameCarousel.pause()
      clearTimeout(this.slideMove)
      this.slideMove = setTimeout(() => this.$refs.nameCarousel.setSlide(this.indexSlide), 400)
    },
  }
};
</script>

<style>
.carousel {
  border-radius: 10px;
  overflow: hidden;
}

.music-carousel{
  position: relative;
  overflow: hidden;
}
</style>
