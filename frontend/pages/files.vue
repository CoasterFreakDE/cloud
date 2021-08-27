<template>
  <div>
    <div id="exp" class="explorer">
      <files @open-preview="togglePreview" :widthV="width" />
      <preview v-show="preview" class="prev"/>
    </div>
    <control />
  </div>
</template>

<script>
import control from "~/components/global/control.vue";
import file from "~/components/explorer/file.vue";
import Files from "~/components/explorer/files.vue";
import Preview from "~/components/explorer/preview.vue";
export default {
  data() {
    return {
      preview: false,
      width: "100vw",
    };
  },
  components: { file, Files, control, Preview },
  methods: {
    getBg() {
      let bg = window.localStorage.getItem("bg");
      if (bg === undefined) bg = "/_nuxt/assets/images/tessst.png";
      let explorer = document.getElementById("exp");
      explorer.style.backgroundImage = `url(${bg})`;
    },
    togglePreview(e) {
      console.log(e)
      // shrink explorer
      this.shrinkExplorer();
      let that = this;
      if (this.preview === true) this.preview = false
      else  setTimeout(function(){that.preview = true}, 450)
     
      
    },
    shrinkExplorer() {
      this.width = this.width === "100vw" ? "900px" : "100vw";
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
  display: flex;
  flex-direction: row;
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

.prev {
  animation: preview;
}

@keyframes preview {
  from {
    display: none;
  }
  to {
    display: block;
    right: 2%;
  }
}
</style>