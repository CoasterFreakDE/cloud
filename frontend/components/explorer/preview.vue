<template>
  <div class="preview">
    <div class="header">
      <p style="margin-left: 15px">filename.png</p>
      <maximize-2-icon class="maximize" />
    </div>
    <div class="preview-ct" style="width: 100%; height: 100%"></div>
    <!-- <div class="footer">
      <div class="button">
        <p class="text">Share</p>
      </div>
      <div class="button">
        <p>Edit</p>
      </div>
      <div class="button" id="delete" style="float: right">
        <p>Delete</p>
      </div>
    </div> -->
  </div>
</template>

<script>
import { Maximize2Icon, ShareIcon } from "vue-feather-icons";
export default {
  components: { Maximize2Icon, ShareIcon },
};
</script>

<style lang="scss" scoped>
.preview {
  background-color: rgba(240, 233, 233, 0.582);
  backdrop-filter: blur(5px);
  height: 650px;
  min-width: 550px;
  width: 550px;
  border-radius: 15px;
  // positioning
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  right: 2%;
  & .header {
    z-index: 4514515;
    position: absolute;
    border-radius: 15px;
    display: flex;
    flex-direction: row;
    height: 50px;
    width: 100%;
    background-color: rgba(240, 233, 233, 0.7);
    line-height: 50px;
    & .maximize {
      position: relative;
      top: 50%;
      left: 70%;
      stroke: rgba(56, 56, 56, 0.733);
      float: right;
      cursor: pointer;
      transform: translate(-50%, -50%);

      &:hover {
        stroke: rgba(58, 58, 58, 0.9);
      }
    }
  }
}
.preview-ct {
  position: relative;
  background-image: url("~assets/images/dog/karsten-winegeart-rs_x0VjRY0U-unsplash.jpg");
  background-size: cover;
  background-position: center center;
  background-repeat: no-repeat;
  bottom: 0;
  border-radius: 15px;
}

.footer {
  position: relative;
  z-index: 454545;
  bottom: 20%;
  right: 0;
  .button {
    cursor: pointer;
    background-color: rgba(240, 233, 233, 0.7);
    height: 40px;
    width: 90px;
    border-radius: 15px;
    line-height: 40px;
    & .ico {
      position: relative;
    }
  }

  #delete {
    background-color: rgba(240, 57, 57, 0.7);
    color: white;
    position: relative;
    right: 15px;
    top: 0%;
    transform: translateY(-50%);
  }
  .text {
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }
}
</style>