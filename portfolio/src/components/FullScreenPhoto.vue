<template>
  <div class="fullscreen" v-if="onFullScreen">
    <div class="operation-btn">
      <img class="prev-btn" src="../assets/pic/slider/prev_photo.png" v-on:click="toPrev" />
      <img class="next-btn" src="../assets/pic/slider/next_photo.png" v-on:click="toNext" />
      <button class="close-btn" v-on:click="toClose">×</button>
    </div>
    <img v-bind:src="photos[photoIndex]" />
  </div>
</template>

<script>
export default {
  name: "FullScreenPhoto",
  computed: {},
  data: function() {
      return {
        photoIndex: 0
      };
   },
  props: {
    onFullScreen: Boolean,
    photos: Array
  },
  methods: {
    toNext() {
      this.photoIndex++;
      if (this.photoIndex > this.$props.photos.length -1) {
        this.photoIndex = 0;
      }
    },
    toPrev() {
      this.photoIndex--;
      if (this.photoIndex < 0) {
        this.photoIndex = this.$props.photos.length - 1;
      }
    },
    toClose() {
      this.$emit("toClose");
    }
  }
};
</script>

<style>
.fullscreen {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0, 0, 0, 0.6);
}

.fullscreen .operation-btn .prev-btn{
    position: absolute;
    top: 25vh;
    left: 45vh; 
}

.fullscreen .operation-btn .next-btn{
    position: absolute;
    top: 25vh;
    right: 45vh; 
}

.fullscreen .operation-btn .close-btn{
    position: absolute;
    top: 22.4vh;
    right: 50.5vh;
    color: red;
}

.fullscreen img {
  padding-top: 25vh;
  max-width: 100%;
  max-height: 100%;
  margin: auto;
}
</style>