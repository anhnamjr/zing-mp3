<template>
  <b-col >
    <div class="music-item">
      <div class="music-item-img">
        <img
        :src="imgUrl"
      />
        <div class="music-item-control">
        <i class="far fa-heart fa-2x"></i>
        <i class="far fa-play-circle fa-4x"></i>
        <i class="fas fa-ellipsis-h fa-2x"></i>
      </div>
      </div>
      <div class="music-item-title">{{ title }}</div>
      
    </div>
  </b-col>
</template>

<script>
export default {
  props: {
    imgUrl: {
      type: String,
      required: true
    },
    title: {
      type: String,
      required: true
    }
  },
  name: "music-item",
};
</script>

<style>
.music-item-img{
  position: relative;
  width: 100%;
  cursor: pointer;
  overflow: hidden;
  border-radius: 5px;
}

.music-item-img:hover .music-item-control{
  visibility: unset;
}

.music-item-img:hover img{
  transform: scale(1.1, 1.1);
}

.music-item-img img {
  width: 100%;
  border-radius: 5px;
  transition: 0.25s;
}

.music-item-title {
  margin-top: 10px;
  font-weight: 700;
  font-size: 18px;
  cursor: pointer;
  word-wrap: break-word;
}

.music-item-title:hover{
  color: #6e55b4;
}

.music-item-control {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: #000;
  opacity: 0.6;
  display: flex;
  border-radius: 5px;
  align-items: center;
  justify-content: space-around;
  visibility: hidden;
}

.music-item-control i{
  color: #fff;
  padding: 5px;
  border-radius: 50%;
  cursor: pointer;
  /* font-weight: lighter; */
}
.music-item-control .fa-2x:hover{
  background: #888;
}
</style>
