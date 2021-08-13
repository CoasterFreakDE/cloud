
<template>
  <modal
    :adaptive="true"
    name="costumize"
    height="auto"
    :scrollable="true"
    :maxWidth="900"
    :width="900"
    class="costumize-modal"
  >
    <h1 style="text-align: center">Costumize your dashboard</h1>
    <h2>Change your background</h2>
    <div class="backgrounds">
      <button
        v-for="image in images"
        :key="image.pathShort"
        class="background"
        :style="{
          backgroundImage: `url(${image.pathLong})`,
        }"
        @click="setBg"
      ></button>
    </div>
    <p style="text-align: center;">All featured images are from <a href="unsplash.com">Unsplash</a> and therefore royalty-free. </p>
  </modal>
</template>

<script>
export default {
  name: "Costumize",
  data() {
    return {
      images: [],
    };
  },
  methods: {
    importAll(r) {
      r.keys().forEach((key) =>
        this.images.push({ pathLong: r(key), pathShort: key })
      );
    },
    setBg(event){
      let button = event.target;
      let bg = button.style.backgroundImage.slice(5, -2)
      this.$emit("bg-change", bg)
    }
  },
  beforeMount() {
    this.importAll(require.context("../assets/images/", true, /\.jpg$/));
  },
};
</script>

<style lang="scss" scoped>
.backgrounds {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.background {
  width: 190px;
  height: 97px;
  margin: 8px;
  background-size: cover;
  background-position: center center;
  text-align: center;
  border-radius: 15px;
  // border: 2px solid blue;
  overflow: hidden;
  &:hover {
    border: 3px solid cadetblue;
  }
}
</style>