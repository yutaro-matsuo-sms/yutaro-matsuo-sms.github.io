<template>
  <div class="photo">
    <img :src="photo" v-on:click.prevent="onPhotoClick" />
  </div>
</template>

<script>
export default {
  name: "Photo",
  components: {},
  props: {
    photo: String,
    index: Number
  },
  data: function() {
    return {
      currentIndex: -1
    };
  },
  methods: {
    onPhotoClick() {
      this.currentIndex = this.$props.index;
      this.$emit("onPhoto", this.currentIndex);
    }
  }
};
</script>

<style>
.photo {
  display: flex;
  align-items: center;
}
</style>