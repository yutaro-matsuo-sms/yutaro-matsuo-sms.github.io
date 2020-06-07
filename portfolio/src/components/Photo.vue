<template>
  <div class="photo">
    <img :src="photo" v-on:click="onPhotoClick"/>
  </div>
</template>

<script>
export default {
  name: "Photo",
  components: {},
  props: {
    photo: String,
  },
  data: function() {
    return {
      ocClickFlag: -1
    };
  },
  methods: {
    onPhotoClick() {
      this.onClickFlag = 11;
      this.$emit("onPhoto", this.onClickFlag);
    }
  }
};
</script>

<style>
.photo {
  display: flex;
  width: 640px;
  height: 420px;
  align-items: center;
}
</style>