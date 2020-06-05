<template>
  <div class="photo">
    <ul class="slide-photo">
      <li>
        <a href="#" v-on:click.prevent="onPhotoClick">
          <img :src="photo" />
        </a>
      </li>
    </ul>
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
  },
};
</script>

<style>
.slide-photo {
  width: 10000px;
  list-style: none;
}

.slide-photo li {
  float: left;
}
</style>