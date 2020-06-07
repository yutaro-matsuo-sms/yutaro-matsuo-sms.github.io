<template>
  <div class="fullscreen" v-if="onFullScreen">
    <div class="operation-btn">
      <button class="close-btn" v-on:click="toClose">×</button>
    </div>
    <img v-bind:src="photos[onClickIndex]" />
  </div>
</template>

<script>
export default {
  name: "FullScreenPhoto",
  computed: {},
  props: {
    onFullScreen: Boolean,
    onClickIndex: Number,
    photos: Array
  },
  methods: {
    toClose() {
      this.$emit("toClose");
    },
  },
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

.fullscreen .operation-btn .close-btn {
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