<template>
  <div>
    <modal @bg-change="setBg"/>
    <div class="dashboard" id="dash">
      <h2 class="greeting">{{ greeting }}, {{ name }}</h2>
      <!--<status/>-->
      <div class="panels">
        <panel
          :title="'Recommended Files'"
          :data="[
            {
              name: 'main.py',
              path: '/test',
              image:
                'https://images.unsplash.com/photo-1617999904549-efcb2671e94c?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
            },
            {
              name: 'message.txt',
              path: '/',
              image:
                'https://images.unsplash.com/photo-1617999904549-efcb2671e94c?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=634&q=80',
            },
          ]"
        />
      </div>
      <div class="footer">
        <button class="costumize-btn" @click="toggleModal">Customize</button>
      </div>
    </div>
  </div>
</template>

<script>
import Modal from '~/components/costumize.vue';
/*import Status from "~/components/status.vue"*/
import Panel from "~/components/panel.vue";
export default {
  components: { /*Status*/ Panel, Modal },
  data() {
    return {
      name: "Leo",
      greeting: "",
      modal: false,
    };
  },
  beforeMount() {
    this.getGreeting();
    window.setInterval(() => {
      this.getGreeting();
    }, 10000);
  },
  methods: {
    getGreeting() {
      const date = new Date();
      const hours = date.getHours();
      let greeting;
      if (hours < 12 && hours >= 5) {
        greeting = "Good morning";
      } else if (hours < 15 && hours >= 12) {
        greeting = "Good day";
      } else if (hours < 22 && hours >= 15) {
        greeting = "Good evening";
      } else {
        greeting = "Good night";
      }
      this.greeting = greeting;
    },
    toggleModal() {
      this.$modal.show("costumize")
    },
    setBg(bg){
      let dashboard = document.getElementById("dash")
      dashboard.style.backgroundImage = `url(${bg})`
    }
  },
};
</script>
<style lang="scss" scoped>
.greeting {
  color: white;
  text-align: center;
  font-size: 32px;
  font-weight: 600;
  line-height: 130%;
  padding: 10vh 16px 0px;
}

.dashboard {
  background-image: url("~assets/images/marek-piwnicki-XdWNaNuEOj4-unsplash.jpg");
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

.costumize-btn {
  text-align: center;
  background-color: rgba(240, 233, 233, 0.582);
  color: white;
  width: 100px;
  height: 40px;
  border-radius: 10px;
}

.footer {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  justify-content: center;
}
.panels {
  width: auto;
  margin: auto;
  max-width: 1500px;
  display: flex;
  justify-content: center;
  flex-direction: row;
  align-items: flex-start;
  flex-wrap: wrap;
}
</style>