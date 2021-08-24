<template>
  <div class="control">
    <div class="clock">
      <p>{{ time }}</p>
    </div>
    <div class="icon-bg">
      <edit-2-icon class="settings" @click="func"/>
    </div>
    <div class="icon-bg">
      <bell-icon class="settings"/>
      <div class="alert"/>
    </div>
    <div class="user" @click="toggleDrop"></div>
    <div id="dropdown-user">
      <p>test</p>
    </div>
  </div>
</template>

<script>
import {Edit2Icon, BellIcon} from "vue-feather-icons"

export default {
  components:{Edit2Icon, BellIcon},
  data() {
    return {
      time: "",
    };
  },
  methods: {
    getTime() {
      const date = new Date();
      this.time = date.toTimeString().split(' ')[0].slice(0, -3)
    },
    toggleDrop(){
      const elem = document.getElementById("dropdown-user");
      elem.classList.toggle("visible")
    },
    func(){
      this.$emit('costumize')
    }
  },
  beforeMount() {
    this.getTime();
    window.setInterval(() => {
      this.getTime();
    }, 10000);
  },
};
</script>

<style lang="scss" scoped>
.control {
  display: flex;
  flex-direction: row;
  z-index: 100000000;
  // positioning
  position: absolute;
  right: 2%;
  top: 2%;
  .clock {
    background: rgba(240, 233, 233, 0.582);
    height: 40px;
    width: 60px;
    border-radius: 15px;
    text-align: center;
    vertical-align: middle;
    & p {
      position: relative;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      color: rgb(70,70,70);
    }
  }
  .user {
      background: url("https://images.unsplash.com/photo-1570500420930-1f3a96f85865?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80");
      width: 40px;
      height: 40px;
      background-size: cover;
      background-repeat: no-repeat;
      border-radius: 100%;
      margin-left: 10px;
      cursor: pointer;
      z-index:inherit;
      background-color:rgba(240, 233, 233, 0.582);
  }
  .icon-bg {
    position: relative;
    background: rgba(240, 233, 233, 0.582);
      width: 40px;
      height: 40px;
      border-radius: 100%;
      margin-left: 10px;
      & .settings {
        stroke: rgba(70, 70, 70, 0.733);
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        cursor:pointer;
      }
      &:hover {
        background: rgba(240, 233, 233, 0.682);
        cursor:pointer;
      }
  }
}

.alert {
  height: 12px;
  width: 12px;
  background: rgba(255, 0, 0, 0.8);
  border-radius: 100%;
  position: absolute;
  top: 80%;
  left: 80%;
  transform: translate(-50%, -50%);
}

.visible {
  display: inherit !important;
}

#dropdown-user {
  z-index: 500000000000;
  position:relative;
  display: none;
  background: rgba(255, 255, 255, 0.726);
  width: 200px;
  height: 300px;
  border-radius: 15px;
  left: 100px;
  top: 10%;
  transform: translate(-50%, -50%);
}
</style>