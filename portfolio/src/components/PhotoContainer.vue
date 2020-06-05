<template>
  <div class="photo-container">
    <h2 class>Contents</h2>
    <Photo
      v-for="(photo, index) in photos"
      :key="photo"
      v-bind:index="index"
      v-bind:photo="photo"
      v-on:onPhoto="onClickPhoto"
    />
    <FullScreenPhoto
      v-bind:onFullScreen="onFullScreen"
      v-bind:photos="photos"
      v-on:toClose="closeFullScreen"
    />
  </div>
</template>

<script>
import Photo from "./Photo";
import FullScreenPhoto from "./FullScreenPhoto";
export default {
  name: "PhotoContainer",
  components: {
    Photo,
    FullScreenPhoto
  },
  props: {
    photos: Array
  },
  data: function() {
    return {
      onFullScreen: false,
    };
  },
  methods: {
    changeFullScreen(index) {
      if (index > -1) {
        return (this.onFullScreen = true);
      }
    },
    onClickPhoto(index) {
      this.changeFullScreen(index);
    },
    closeFullScreen() {
        this.onFullScreen = false;
    }
  },
};
</script>

<style>
.photo-container {
  width: 100%;
  max-width: 640px;
  overflow: hidden;
  position: relative;
  margin: 0 auto;
}
</style>