<template>
  <div id="app">
    <b-row id="title-row">
      <b-col class="text-right">
        <img alt="Riley" id="riley" src="./assets/riley.png" />
      </b-col>
      <b-col class="text-left">
        <h1>Riley's</h1>
        <h1>Prize</h1>
        <h1>Shop</h1>
      </b-col>
      <!-- TODO
      <b-col>
        How many tickets do you have?
      </b-col> -->
    </b-row>
    <b-row>
      <b-col>
        <Prize
          title="First Prize"
          imgSrc="https://via.placeholder.com/250"
          :numberOfTickets="5"
          url=""
        />
      </b-col>
      <b-col>
        <Prize
          title="Second Prize"
          imgSrc="https://via.placeholder.com/250"
          :numberOfTickets="10"
          url=""
        />
      </b-col>
      <b-col>
        <Prize
          title="Third Prize"
          imgSrc="https://via.placeholder.com/250"
          :numberOfTickets="15"
          url=""
        />
      </b-col>
    </b-row>
  </div>
</template>

<script>
import Vue from "vue";
import Prize from "./components/Prize.vue";
import { BootstrapVue, IconsPlugin } from "bootstrap-vue";

// Import Bootstrap an BootstrapVue CSS files
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-vue/dist/bootstrap-vue.css";

// Make BootstrapVue available project
Vue.use(BootstrapVue);
// Install the BootstrapVue icon components plugin
Vue.use(IconsPlugin);

export default {
  name: "App",
  components: {
    Prize,
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#title-row{
  margin-bottom: 50px;
}

h1 {
  margin-bottom: 25px;
  color: white;
  font-family: "Pacifico", cursive;
  font-size: 5rem;
}

#riley {
  max-height: 350px;
}
</style>
