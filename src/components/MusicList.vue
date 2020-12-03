<template>
  <b-row>
    <music-item></music-item>
    <music-item></music-item>
    <music-item></music-item>
    <music-item></music-item>
    <music-item></music-item>
  </b-row>
</template>

<script>
import MusicItem from "@/components/MusicItem";
export default {
  name: "music-list",
  components: {
    MusicItem,
  },
};
</script>

<style></style>
