<template>
  <div id="app">
    <header-bar />
    <router-view />
  </div>
</template>

<script>
import HeaderBar from "@/components/HeaderBar"
export default {
  components: {HeaderBar}
}
</script>

<style></style>
