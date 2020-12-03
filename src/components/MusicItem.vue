<template>
  <b-col>
    <div class="music-item">
      <img
        src="https://photo-resize-zmp3.zadn.vn/w480_r1x1_jpeg/cover/6/c/a/9/6ca9daecf773ef8e8243e37c8ae227b8.jpg"
      />
      <div>Giáng Sinh Đã Về</div>
    </div>
  </b-col>
</template>

<script>
export default {
  props: {},
  name: "music-item",
};
</script>

<style>
.music-item img {
  width: 100%;
  border-radius: 5px;
}

.music-item div {
  margin-top: 10px;
  font-weight: 700;
  font-size: 18px;
}
</style>
