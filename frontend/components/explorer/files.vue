<template>
  <div class="overview" :style="{ width: widthV }">
    <div class="header">
      <div class="icobg">
        <arrow-left-icon class="back-icon" size="1.5x" />
      </div>
      <breadcrumbs
        style="margin-left: 10px"
        :crumbs="[
          { name: 'Documents', url: 'documents' },
          { name: 'private', url: 'private' },
        ]"
      />
    </div>
    <table>
      <thead>
        <tr>
          <th>Name</th>
          <th>Size</th>
          <th>Last changed</th>
          <th>Changed by</th>
        </tr>
      </thead>
      <tbody>
        <tr @click="openInPreview">
          <td class="ico">
            <file-icon class="file-icon" />
            <p>image.py</p>
          </td>
          <td id="test">1,3 MB</td>
          <td>16.0.6</td>
          <td>user</td>
        </tr>
        <tr @click="openInPreview">
          <td class="ico">
            <image-icon class="file-icon" />
            <p>upload.png</p>
          </td>
          <td>0.3 kB</td>
          <td>16.0.4</td>
          <td>Cheetah</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
import { ArrowLeftIcon, ImageIcon, FileIcon } from "vue-feather-icons";
import Breadcrumbs from "./breadcrumbs.vue";
export default {
  components: { ArrowLeftIcon, Breadcrumbs, ImageIcon, FileIcon },
  props: ["widthV"],
  mounted() {
    console.log(this.widthV);
  },
  methods: {
    openInPreview(e) {
      let target = e.target;
      let targets = document.getElementsByClassName("active-row");
      for (let t of targets) {
        t.classList.toggle("active-row");
      }
      if (target.nodeName == "TD")
        target.parentElement.classList.toggle("active-row");
      this.$emit("open-preview", "test");
    },
  },
};
</script>

<style lang="scss" scoped>
.overview {
  background-color: rgba(240, 233, 233, 0.582);
  backdrop-filter: blur(5px);
  height: 650px;
  min-width: 900px;
  max-width: 90vw;
  border-radius: 15px;
  transition: all 0.5s linear;
  // positioning
  position: absolute;
  top: 50%;
  left: 6%;
  transform: translateY(-50%);
  & .header {
    background-color: rgba(240, 233, 233, 0.7);
    width: 100%;
    height: 50px;
    border-radius: 15px;
    display: flex;
    flex-direction: row;
    line-height: 50px;
    & .back-icon {
      stroke: rgba(56, 56, 56, 0.733);
      cursor: pointer;
      position: relative;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);

      &:hover {
        stroke: rgba(58, 58, 58, 0.9);
      }
    }
    & .icobg {
      background-color: rgba(240, 233, 233, 0.85);
      border-radius: 15px;
      height: 50px;
      width: 50px;
      cursor: pointer;
    }
  }
}
table {
  width: 100%;
}
th {
  color: rgba(56, 56, 56, 0.85);
}
td {
  text-align: center;
  color: rgba(56, 56, 56, 0.75);
  cursor: pointer;
}
.active-row {
  background-color: rgba(240, 233, 233, 0.6);
}

.file-icon {
  stroke: rgba(56, 56, 56, 0.733);
}
p {
  margin-left: 5px;
}
.ico {
  display: flex;
  justify-content: center;
}
</style>