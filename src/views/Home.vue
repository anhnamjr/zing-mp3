<template>
  <div class="home">
    <music-carousel :musicData="musicData" />
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
        v-for="(musicList, index) in musicLists"
        :key="index"
        :numItem="5"
        :musicList="musicList.musics"
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
        <b-col v-for="(chart, index) in musicChart" :key="index">
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
import MusicCarousel from "@/components/MusicCarousel";
import MusicList from "@/components/MusicList";
import MusicImageItem from "@/components/MusicImageItem";
import MusicSinger from "@/components/MusicSinger";
export default {
  name: "Home",
  components: { MusicCarousel, MusicList, MusicImageItem, MusicSinger },
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
      ],
      musicLists: [
        {
          title: "Click nghe là thích",
          musics: [
            {
              id: 0,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/9/3/2/4/93241b5e2dbd479b5c257b93ce2beb3c.jpg",
              title: "Your XMAS List",
            },
            {
              id: 1,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/3/9/7/7/3977856a8f720fe3da97498061367aaa.jpg",
              title: "Rap Việt Tạo Động Lực",
            },
            {
              id: 2,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/d/a/e/9/dae92123e7c55939e2aed04ea1bc189f.jpg",
              title: "Một Bước Thành Sao",
            },
            {
              id: 3,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/1/0/c/4/10c485468a36a0222364d45a8c261027.jpg",
              title: "Gửi Lời Yêu Thương",
            },
            {
              id: 4,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/2/d/6/3/2d63cf92d408126969202b2d7236cdc7.jpg",
              title: "R&B Việt Ngày Nay",
            },
            {
              id: 5,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/e/d/8/f/ed8fd16d327aa4acdf222c25ece3a109.jpg",
              title: "Nhạc Pop Cho Ngày Giáng Sinh",
            },
            {
              id: 6,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/d/b/8/c/db8c5772bf16c2d561d13440ad59bd6c.jpg",
              title: "K-Pop Today!",
            },
            {
              id: 7,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/a/7/a/6/a7a62ac7aac295c457d123468ceaa460.jpg",
              title: "C-Pop Hot Covers",
            },
            {
              id: 8,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/5/a/8/4/5a847d4cb94ff6852a9438e5e6f566d5.jpg",
              title: "K-Pop Happy Whistle",
            },
            {
              id: 9,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/3/a/2/7/3a276c999618c9d492803ea7709f76ea.jpg",
              title: "OMG: Dance Pop Thời Nay",
            },
          ],
        },
        {
          title: "Rộn ràng nhạc mới",
          musics: [
            {
              id: 0,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/0/f/7/2/0f72a309c8ff3a96aaeba9e38ef2ebf0.jpg",
              title: "Nhạc Hàn Hôm Nay Nghe Gì?",
            },
            {
              id: 1,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/b/6/1/e/b61e8a4e10a506e1329a34742b8396ff.jpg",
              title: "Today's Country Hits",
            },
            {
              id: 2,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/8/c/f/9/8cf949a6142c633675ba354dd10d3428.jpg",
              title: "Đỉnh Cao TRENDING",
            },
            {
              id: 3,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/6/7/0/0/6700cd729613d697be0ddf185cca9e6d.jpg",
              title: "V-Pop Nhạc Mới Nổi Bật",
            },
            {
              id: 4,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/e/3/1/2/e312a5ccc373ddb2e4a6c69bfb0877ba.jpg",
              title: "Today's R&B Hits",
            },
            {
              id: 5,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/7/c/d/1/7cd125876e0f96427536af0bde2a36c8.jpg",
              title: "Today's Top Hits",
            },
            {
              id: 6,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/d/b/8/c/db8c5772bf16c2d561d13440ad59bd6c.jpg",
              title: "K-Pop Today!",
            },
            {
              id: 7,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/a/7/a/6/a7a62ac7aac295c457d123468ceaa460.jpg",
              title: "C-Pop Hot Covers",
            },
            {
              id: 8,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/5/a/8/4/5a847d4cb94ff6852a9438e5e6f566d5.jpg",
              title: "K-Pop Happy Whistle",
            },
            {
              id: 9,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/3/a/2/7/3a276c999618c9d492803ea7709f76ea.jpg",
              title: "OMG: Dance Pop Thời Nay",
            },
          ],
        },
        {
          title: "Mỉm cười cho ngày vui",
          musics: [
            {
              id: 0,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/4/b/e/e/4bee634cb31f13833ec650aa4fabb911.jpg",
              title: "Nghe Thôi... Đã Thấy Vui!",
            },
            {
              id: 1,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/e/3/4/f/e34f647ec174b4b19c4cb1f01231fd8a.jpg",
              title: "Teen Pop",
            },
            {
              id: 2,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/4/4/8/8/44883b3adab9e51e7e36dcf3cb754a00.jpg",
              title: "K-Pop Cute",
            },
            {
              id: 3,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/4/2/6/f/426f70ed262e2bf0a7289216ec636559.jpg",
              title: "Nhạc Hoa Hot Trên Mạng Xã Hội",
            },
            {
              id: 4,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/7/7/3/8/7738daae1b9090b9890336cfc13c371e.jpg",
              title: "Life Is Good",
            },
            {
              id: 5,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/7/c/d/1/7cd125876e0f96427536af0bde2a36c8.jpg",
              title: "Today's Top Hits",
            },
            {
              id: 6,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/d/b/8/c/db8c5772bf16c2d561d13440ad59bd6c.jpg",
              title: "K-Pop Today!",
            },
            {
              id: 7,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/a/7/a/6/a7a62ac7aac295c457d123468ceaa460.jpg",
              title: "C-Pop Hot Covers",
            },
            {
              id: 8,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/5/a/8/4/5a847d4cb94ff6852a9438e5e6f566d5.jpg",
              title: "K-Pop Happy Whistle",
            },
            {
              id: 9,
              imgUrl:
                "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/3/a/2/7/3a276c999618c9d492803ea7709f76ea.jpg",
              title: "OMG: Dance Pop Thời Nay",
            },
          ],
        },
      ],
      musicChart: [
        {
          imgUrl: "//static-zmp3.zadn.vn/skins/zmp3-v5.2/images/song-vn-2x.jpg",
        },
        { imgUrl: "//static-zmp3.zadn.vn/skins/zmp3-v5.2/images/mv-vn-2x.jpg" },
        {
          imgUrl:
            "//static-zmp3.zadn.vn/skins/zmp3-v5.2/images/web_song_usuk.png",
        },
        {
          imgUrl:
            "//static-zmp3.zadn.vn/skins/zmp3-v5.2/images/web_song_kpop.png",
        },
      ],
    };
  },
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
