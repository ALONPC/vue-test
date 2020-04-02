<template>
  <img :src="picture.image.url" />
</template>

<script>
export default {
  name: "Picture",
  props: {
    picture: {
      type: Object,
      required: true
    }
  },
  data() {
    this.picture.image.url;
  },
  mounted() {
    console.log("picture", this.picture);
  }
};
</script>
