<template>
  <div class="home">
    <music-carousel :musicData="musicData" :nameCarousel="'crs1'" />
    <!-- Header Login -->
    <b-container class="pt-5">
      <div class="login-header">
        <img
          src="https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/logo-mp-3.png"
          width="40px"
          height="40px"
        />
        <span
          >Hãy đăng nhập để khám phá thêm nhiều bài hát dành riêng cho bạn</span
        >
        <b-button variant="warning">ĐĂNG NHẬP</b-button>
      </div>
    </b-container>
    <!-- List -->
    <b-container fluid="sm" class="pt-5 p-0 sm">
      <music-list></music-list>
    </b-container>
  </div>
</template>

<script>
import MusicCarousel from "@/components/MusicCarousel";
import MusicList from "@/components/MusicList";
export default {
  name: "Home",
  components: { MusicCarousel, MusicList },
  data() {
    return {
      musicData: [
        {
          imgUrl:
            "https://photo-zmp3.zadn.vn/banner/1/3/e/2/13e23dfe2c5eb64b73b811962ec1e634.jpg",
        },
        {
          imgUrl:
            "https://photo-zmp3.zadn.vn/banner/b/a/5/3/ba53ac8d31b01866a4bfd98cc24d2705.jpg",
        },
        {
          imgUrl:
            "https://photo-zmp3.zadn.vn/banner/d/d/3/a/dd3ac08d733a90ee48c6a7a209ba8b53.jpg",
        },
        {
          imgUrl:
            "https://photo-zmp3.zadn.vn/banner/7/a/8/d/7a8d688a3211153f5c7003a942a84dd8.jpg",
        },
        {
          imgUrl:
            "https://photo-zmp3.zadn.vn/banner/1/2/e/7/12e7a0ae78122ecda43d817ec1664f0b.jpg",
        },
      ]
    };
  }
};
</script>

<style>
.login-header {
  height: 70px;
  background-image: url("https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/banner-bg.svg");
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  border-radius: 5px;
  padding: 0 100px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.login-header span {
  color: #fff;
  font-weight: 800;
  font-size: 20px;
}

.login-header button {
  color: #fff;
  font-weight: 700;
}
.login-header button:hover {
  color: #6e55b4 !important;
  background: #fff !important;
  border: #fff !important;
}
</style>
