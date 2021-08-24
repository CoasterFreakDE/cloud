<template>
  <div>
    <div id="exp" class="explorer">
      <div class="ct">
        <file :type="'folder'" :name="'Documents'" :shared="false" />
        <file :type="'file'" :name="'main.py'" :shared="false" />
      </div>
    </div>
  </div>
</template>

<script>
import file from "~/components/explorer/file.vue";
export default {
  components: { file },
  methods: {
    getBg() {
      let bg = window.localStorage.getItem("bg");
      if (bg === undefined) bg = "/_nuxt/assets/images/tessst.png";
      let explorer = document.getElementById("exp");
      explorer.style.backgroundImage = `url(${bg})`;
    },
  },
  mounted() {
    this.getBg();
  },
};
</script>

<style lang="scss" scoped>
.explorer {
  width: 100%;
  min-height: 100vh;
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  background-color: white;
  --color-background-translucent: rgba(255, 255, 255, 0.8);
  --background-blur: blur(10px);
}
.ct {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  width: 80%;
  height: auto;
  // flex
  display: flex;
  flex-direction: row;
}
</style>