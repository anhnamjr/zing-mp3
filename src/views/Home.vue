<template>
  <div class="home">
    <music-carousel :musicData="allMusicHots" />
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
      <music-list
        v-for="(musicList, index) in allMusicLists"
        :key="index"
        :numItem="5"
        :musicList="musicList.musicList"
        :title="musicList.title"
      />

      <b-row>
        <img
          class="m-auto"
          src="https://scontent.fsgn2-5.fna.fbcdn.net/v/t1.15752-9/130052141_196529588842551_7164164433942660137_n.png?_nc_cat=102&cb=846ca55b-ee17756f&ccb=2&_nc_sid=ae9488&_nc_ohc=2VLy7Dwg-H4AX-MxAnq&_nc_ht=scontent.fsgn2-5.fna&oh=4aabb932b1fce6a9100cd90ba59f5028&oe=5FF279F9"
          width="1145px"
        />
      </b-row>

      <b-row class="mb-3 mt-3 m">
        <b-col v-for="(chart, index) in allMusicChart" :key="index">
          <music-image-item
            :imgUrl="chart.imgUrl"
            :fullOpt="0"
            :opacity="0"
            height="60px"
          />
        </b-col>
      </b-row>

      <b-carousel :interval="3000" class="mb-5">
        <b-carousel-slide>
          <template #img>
            <b-row>
              <b-col>
                <music-singer
                  imgUrl="https://photo-resize-zmp3.zadn.vn/w240_r1x1_jpeg/avatars/3/a/6/d/3a6de9f068f10fcee2c50cdf9772ebaa.jpg"
                  nameSinger="Justatee"
                />
              </b-col>
              <b-col>
                <music-singer
                  imgUrl="https://photo-resize-zmp3.zadn.vn/w240_r1x1_jpeg/avatars/f/1/d/d/f1ddeb86e263f0d67f835f1b60539a34.jpg"
                  nameSinger="SOOBIN"
                />
              </b-col>
              <b-col>
                <music-singer
                  imgUrl="https://photo-resize-zmp3.zadn.vn/w240_r1x1_jpeg/avatars/5/9/7/c/597c5594c732d3857de91b16156f7f32.jpg"
                  nameSinger="Trịnh Thăng Bình"
                />
              </b-col>
            </b-row>
          </template>
        </b-carousel-slide>
        <b-carousel-slide>
          <template #img>
            <b-row>
              <b-col>
                <music-singer
                  imgUrl="https://photo-resize-zmp3.zadn.vn/w240_r1x1_jpeg/avatars/0/e/c/d/0ecdb1dcda7c80241efaeda1ac44fabe.jpg"
                  nameSinger="Will"
                />
              </b-col>
              <b-col>
                <music-singer
                  imgUrl="https://photo-resize-zmp3.zadn.vn/w240_r1x1_jpeg/avatars/e/1/1/2/e1120261421cfec7513423222b0ca94c.jpg"
                  nameSinger="Mr Siro"
                />
              </b-col>
              <b-col>
                <music-singer
                  imgUrl="https://photo-resize-zmp3.zadn.vn/w240_r1x1_jpeg/avatars/5/b/b/9/5bb9687f3e038e91ea96aa9dae5457ff.jpg"
                  nameSinger="MIN"
                />
              </b-col>
            </b-row>
          </template>
        </b-carousel-slide>
      </b-carousel>
    </b-container>
  </div>
</template>

<script>
import { mapGetters } from "vuex"

import MusicCarousel from "@/components/MusicCarousel";
import MusicList from "@/components/MusicList";
import MusicImageItem from "@/components/MusicImageItem";
import MusicSinger from "@/components/MusicSinger";
export default {
  name: "Home",
  components: { MusicCarousel, MusicList, MusicImageItem, MusicSinger },
  computed: mapGetters(["allMusicHots", "allMusicLists", "allMusicChart"])
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
