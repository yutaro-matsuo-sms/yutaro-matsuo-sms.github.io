<template>
  <div class="photo-container">
    <carousel 
      :autoplay="true" 
      :loop="true" 
      :speed="1000" 
      :per-page="1"
      @pageChange="getIndex"
    >
      <slide v-for="photo in photos" :key="photo.index">
        <div class="photo-slider">
          <Photo
            v-bind:photo="photo" 
            v-on:onPhoto="onClickPhoto" 
          />
        </div>
      </slide>
    </carousel>
    <FullScreenPhoto
      v-bind:onFullScreen="onFullScreen"
      v-bind:onClickIndex="onClickIndex"
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
      onFullScreen: false,
      onClickIndex: 0
    };
  },
  methods: {
    changeFullScreen(Flag) {
      if (Flag > 10) {
        return (this.onFullScreen = true);
      }
    },
    onClickPhoto(n) {
      const onClickFlag = this.onClickIndex + n;
      this.changeFullScreen(onClickFlag);
    },
    getIndex(index) {
      if (this.onFullScreen === false ) {
        this.onClickIndex = index;
      }
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

.photo-slider {
  margin: 0, auto;
}
</style>