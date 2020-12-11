<template>
  <b-container>
    <b-row>
      <b-col></b-col>
      <b-col></b-col>
    </b-row>
  </b-container>
</template>

<script>
import { mapGetters } from "vuex";

export default { 
  name: "Album",
  computed: mapGetters(["allMusicLists"]),
  data(){
    return {
      currentAlbum: null
    }
  },
  methods: {
    findAlbum: function(title) {
      let result = undefined
      this.allMusicLists.forEach(list => {
        let res = list.musicList.find(item => this.$convertTitleToLink(item.title) === title)
        if(res){
          result = res
        }
      })
      return result;
    }
  },
  created(){
    this.currentAlbum = this.findAlbum(this.$route.params.title)
  }
}
</script>

<style>

</style>