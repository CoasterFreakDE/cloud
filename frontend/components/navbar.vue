<template>
  <header>
    <div class="left">
      <ul class="apps">
        <li>
          <a>Dashboard</a>
          <a>Dashboard</a>
          <a>Dashboard</a>
        </li>
      </ul>
    </div>
    <div class="right"></div>
  </header>
</template>

<script>
import { HomeIcon, FolderIcon } from "vue-feather-icons";
export default {
  components: { HomeIcon, FolderIcon },
};
</script>

<style lang="scss" scoped>
.apps {
  display: inline-flex;
  min-width: 50px;
  z-index: 2;
  list-style: none;
  float: left;
  & li {
    position: relative;
    cursor: pointer;
    padding: 0 2px;
    display: flex;
    justify-content: center;
    &a {
        color: white;
        margin-left: 10px;
    }
  }
}
.bernercloud {
  padding: 7px 0;
  padding-left: 0px;
  padding-left: 86px;
  position: relative;
  height: 100%;
  box-sizing: border-box;
  opacity: 1;
  align-items: center;
  display: flex;
  flex-wrap: wrap;
  overflow: hidden;
  float: left;
}
.logo {
  display: inline-flex;
  background-repeat: no-repeat;
  background-size: contain;
  background-position: center;
  width: 62px;
  position: absolute;
  left: 12px;
  top: 1px;
  bottom: 1px;
}
header {
  display: inline-flex;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 2000;
  height: 50px;
  justify-content: space-between;
  box-sizing: border-box;
}

.right {
  justify-content: flex-end;
  align-items: center;
}

.left {
  flex: 0 1;
  white-space: nowrap;
  min-width: none;
}

.icon {
    &:hover {
        stroke: #fff
    }
}

.icon-active {
    stroke: #fff;
}
</style>