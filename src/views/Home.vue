<template>
  <div class="home">
    <!-- <header-bar /> -->
    <b-container class="p-0">
      <b-carousel
        img-height="480px"
        img-width="100%"
        :interval="3000"
        @sliding-start="onSlideStart"
        @sliding-end="onSlideEnd"
        
      >
        <b-carousel-slide
          class="rounded"
          img-src="https://photo-zmp3.zadn.vn/banner/1/3/e/2/13e23dfe2c5eb64b73b811962ec1e634.jpg"
        ></b-carousel-slide>
        <b-carousel-slide
          img-src="https://photo-zmp3.zadn.vn/banner/b/a/5/3/ba53ac8d31b01866a4bfd98cc24d2705.jpg"
        >
        </b-carousel-slide>
        <b-carousel-slide
          img-src="https://photo-zmp3.zadn.vn/banner/d/d/3/a/dd3ac08d733a90ee48c6a7a209ba8b53.jpg"
        >
        </b-carousel-slide>
        <b-carousel-slide
          img-src="https://photo-zmp3.zadn.vn/banner/7/a/8/d/7a8d688a3211153f5c7003a942a84dd8.jpg"
        >
        </b-carousel-slide>
        <b-carousel-slide
          img-src="https://photo-zmp3.zadn.vn/banner/1/2/e/7/12e7a0ae78122ecda43d817ec1664f0b.jpg"
        >
        </b-carousel-slide>
      </b-carousel>
    </b-container>
  </div>
</template>

<script>
// import HeaderBar from "@/components/HeaderBar";
export default {
  name: "Home",
  // components: { HeaderBar }
};
</script>

<style>
.carousel {
  border-radius: 10px;
  overflow: hidden;
}
</style>