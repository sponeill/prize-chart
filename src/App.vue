<template>
  <div id="app">
    <b-row id="title-row">
      <b-col class="text-right" lg=3>
        <img alt="Riley" id="riley" src="./assets/riley.png" />
      </b-col>
      <b-col class="text-left" lg=2>
        <h1>Riley's</h1>
        <h1>Prize</h1>
        <h1>Shop</h1>
      </b-col>
      <b-col lg=4>
        <TicketCounter @ticketsAdded="ticketsAdded($event)"></TicketCounter>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <Prize
          title="First Prize"
          imgSrc="https://via.placeholder.com/175"
          :ticketCost="5"
          :currentTickets= this.currentTickets
          url=""
        />
      </b-col>
      <b-col>
        <Prize
          title="Second Prize"
          imgSrc="https://via.placeholder.com/175"
          :ticketCost="10"
          :currentTickets= this.currentTickets
          url=""
        />
      </b-col>
      <b-col>
        <Prize
          title="Third Prize"
          imgSrc="https://via.placeholder.com/175"
          :ticketCost="15"
          :currentTickets= this.currentTickets
          url=""
        />
      </b-col>
      <b-col>
        <Prize
          title="Fourth Prize"
          imgSrc="https://via.placeholder.com/175"
          :ticketCost="20"
          :currentTickets= this.currentTickets
          url=""
        />
      </b-col>
    </b-row>
  </div>
</template>

<script>
import Vue from "vue";
import Prize from "./components/Prize.vue";
import TicketCounter from "./components/TicketCounter.vue";
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
    TicketCounter,
  },
  data: function () {
      return {
        currentTickets: 0,
      };
  },
  methods: {
    ticketsAdded: function (ticketNumber) {
      this.currentTickets = ticketNumber;
      console.log("Parent Ticket Count: " + ticketNumber);
    }
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

#title-row {
  margin-bottom: 50px;
}

h1 {
  margin-bottom: 25px;
  color: white;
  font-family: "Pacifico", cursive;
  font-size: 4rem;
}

#riley {
  max-height: 275px;
}
</style>
