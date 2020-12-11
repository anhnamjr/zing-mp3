<template>
  <b-col>
    <router-link :to="{name: 'Album', params: {title: link}}" tag="div">
      <div class="music-item">
        <music-image-item :imgUrl="imgUrl" />
        <div class="music-item-title">{{ title }}</div>
      </div>
    </router-link>
  </b-col>
</template>

<script>
import MusicImageItem from "@/components/MusicImageItem";
export default {
  components: {
    MusicImageItem,
  },
  props: {
    imgUrl: {
      type: String,
      required: true,
    },
    title: {
      type: String,
      required: true,
    },
    width: {
      type: String,
      default: "100%",
    },
    height: {
      type: String,
    },
  },
  name: "music-item",
  computed: {
    link: function() {
      let scope = this;
      return this.$convertTitleToLink(scope.title);
    },
  },
};
</script>

<style>
.music-item-title {
  margin-top: 10px;
  font-weight: 700;
  font-size: 18px;
  cursor: pointer;
  word-wrap: break-word;
}

.music-item-title:hover {
  color: #6e55b4;
}
</style>
