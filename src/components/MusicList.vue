<template>
  <div class="music-list mb-3">
    <div class="music-list-title mb-3">
      <span>{{ title }}</span>
      <div class="music-list-controls">
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
    <b-carousel :interval="0" ref="myCarousel">
      <b-carousel-slide v-for="slide in numSlide" :key="slide">
        <template v-slot:img>
          <b-row
            v-if="
              dataTest.slice((slide - 1) * numItem, slide * numItem).length ===
                numItem
            "
          >
            <music-item
              v-for="item in dataTest.slice(
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
              v-for="item in dataTest.slice(
                (slide - 1) * numItem,
                slide * numItem
              )"
              :key="item.id"
              :imgUrl="item.imgUrl"
              :title="item.title"
            />
            <b-col
              v-for="remainNum in Math.abs(
                dataTest.slice((slide - 1) * numItem, slide * numItem).length -
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
// import VueSlickCarousel from "vue-slick-carousel";
export default {
  name: "music-list",
  props: {
    title: {
      type: String,
      required: true,
    },
    numItem: {
      type: Number,
    },
  },
  components: {
    MusicItem,
  },
  data() {
    return {
      dataTest: [
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
            "https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/6/7/0/0/6700cd729613d697be0ddf185cca9e6d.jpg",
          title: "V-Pop Nhạc Mới Nổi Bật",
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
      currentSlide: 1,
    };
  },
  computed: {
    numSlide: function() {
      return Math.ceil(this.dataTest.length / this.numItem);
    },
  },
  methods: {
    nextSlide(){
      if(this.currentSlide < this.numSlide){
        this.$refs.myCarousel.next()
        this.currentSlide++
      }
    },

    prevSlide(){
      if(this.currentSlide > 1){
        this.$refs.myCarousel.prev()
        this.currentSlide--
      }
    }
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
