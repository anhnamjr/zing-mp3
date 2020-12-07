<template>
  <div class="music-singer">
    <music-image-item
      width="35%"
      height="35%"
      :imgUrl="imgUrl"
      :rounded="true"
      :fullOpt="1"
      :opacity="0"
    />
    <div class="music-singer-name">
      <span class="zing-choice"> <i class="fas fa-star"></i> ZING CHOICE </span>
      <div>
        {{ nameSinger }}
      </div>
    </div>
  </div>
</template>

<script>
import MusicImageItem from "@/components/MusicImageItem";
export default {
  name: "music-singer",
  props: {
    imgUrl: {
      type: String,
      required: true,
    },
    nameSinger: {
      type: String,
      required: true,
    },
  },
  components: { MusicImageItem },
};
</script>

<style>
.music-singer {
  display: flex;
  justify-content: space-between;
  padding: 1rem;
  align-items: center;
  background-image: url(https://zjs.zadn.vn/zmp3-desktop/releases/v0.2.6/images/spotlight-bg.jpg);
  background-size: cover;
  background-position: center;
  border-radius: 5px;
  width: 100%;
}

.zing-choice {
  background: linear-gradient(to right, #f508b7, #9102ff);
  color: #fff;
  font-size: small;
  padding: 3px 5px;
  border-radius: 5px;
  margin-bottom: 5px;
}

.music-singer-name {
  font-size: 1.5rem;
  font-weight: 700;
  text-align: end;
  /* min-width: 60%; */
}
</style>
