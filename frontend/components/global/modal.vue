<template>
  <div id="modal" :style="{ height: `${height}`, width: `${width}` }">
    <button @click="close" class="close">
      <x-icon class="close-icon" />
    </button>

    <slot />
  </div>
</template>

<script>
import { XIcon } from "vue-feather-icons";
export default {
  props: ["width", "height"],
  components: { XIcon },
  methods: {
    close() {
      this.$emit("close-modal");
    },
  },
};
</script>

<style lang="scss" scoped>
#modal {
  z-index: 999999999999999999;
  // styling
  background-color: rgba(255, 255, 255, 0.801);
  border-radius: 15px;
  // positioning
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.close {
  position: absolute;
  top: 2.5%;
  right: 2.5%;
  margin-bottom: 10px;
}
.close-icon {
  stroke: rgba(70, 70, 70, 0.733);
  cursor: pointer;
  &:hover {
    stroke: rgba(70, 70, 70, 0.9);
  }
}
</style>