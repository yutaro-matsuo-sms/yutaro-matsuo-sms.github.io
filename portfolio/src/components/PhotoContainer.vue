<template>
  <div class="photo-container">
    <carousel 
      :autoplay="true" 
      :loop="true" 
      :speed="1000"
      :per-page="1">
      <slide v-for="photo in photos" :key="photo.index">
        <Photo 
          v-bind:index="index" 
          v-bind:photo="photo" 
          v-on:onPhoto="onClickPhoto" 
        />
      </slide>
    </carousel>
    <FullScreenPhoto
      v-bind:onFullScreen="onFullScreen"
      v-bind:photos="photos"
      v-on:toClose="closeFullScreen"
    />
  </div>
</template>

<script>
import { Carousel, Slide } from "vue-carousel";
import Photo from "./Photo";
import FullScreenPhoto from "./FullScreenPhoto";
export default {
  name: "PhotoContainer",
  components: {
    Carousel,
    Slide,
    Photo,
    FullScreenPhoto
  },
  props: {
    photos: Array
  },
  data: function() {
    return {
      onFullScreen: false
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
  }
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