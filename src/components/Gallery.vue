<template>
  <div>
    <div class="gallery">
      <div
        class="uk-grid-small uk-grid-column-small uk-grid-row-small uk-grid-match uk-grid"
        uk-grid="masonry: true"
      >
        <div v-for="(picture, index) in this.pictures" :key="index">
          <div class="uk-animation-toggle" tabindex="0">
            <div class="pictureContainer uk-animation-kenburns">
              <Picture :picture="picture" class="picture uk-img" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import Picture from "./Picture.vue";

export default {
  name: "Gallery",
  components: {
    Picture
  },
  data() {
    return {
      pictures: []
    };
  },
  props: {
    msg: String
  },
  mounted() {
    axios
      .get("https://api.ameiz.cl/api/v1/professionals/portfolios")
      .then(res => {
        console.log(res.data);
        this.pictures = res.data;
        console.log("mounted -> pictures", this.pictures);
      });

    console.log(this.pictures);
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.pictureContainer {
  padding: 5px;
  max-width: 252px;
}

.picture {
  max-height: 100%;
}

.gallery {
  margin: 100px;
}
</style>
