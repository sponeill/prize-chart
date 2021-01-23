<template>
  <div id="app">
    <b-row id="title-row">
      <b-col class="text-right" lg="4">
        <img alt="Riley" id="riley" src="./assets/riley.png" />
      </b-col>
      <b-col lg="4">
        <h1>Riley's Prize Shop</h1>
        <TicketCounter @ticketsAdded="ticketsAdded($event)"></TicketCounter>
      </b-col>
      <b-col>
        <div id="ticket">
          <p id="ticket-counter">
            <span>{{ currentTickets }}</span> Tickets Left
          </p>
        </div>
      </b-col>
    </b-row>
    <b-row>
      <b-col>
        <Prize
          title="Stay Up Late"
          imgSrc="../img/stay_up.png"
          :ticketCost="3"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
      <b-col>
        <Prize
          title="Donuts"
          imgSrc="../img/donuts.png"
          :ticketCost="4"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
      <b-col>
        <Prize
          title="Smoothies"
          imgSrc="../img/pulp.png"
          :ticketCost="4"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
      <b-col>
        <Prize
          title="Riley Picks Dinner"
          imgSrc="../img/dinner.png"
          :ticketCost="5"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
    </b-row>
    <b-row id="bottom-row">
      <b-col>
        <Prize
          title="Sing"
          imgSrc="../img/sing.png"
          :ticketCost="7"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
      <b-col>
        <Prize
          title="Barbie Car"
          imgSrc="../img/barbie_car.png"
          :ticketCost="15"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
      <b-col>
        <Prize
          title="Doll Accessories"
          imgSrc="../img/american_girl.png"
          :ticketCost="15"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
        />
      </b-col>
      <b-col>
        <Prize
          title="Princess Dress"
          imgSrc="../img/princess_dress.png"
          :ticketCost="20"
          :currentTickets="this.currentTickets"
          url=""
          :prizesShown="this.prizesShown"
          @prizeSelected="prizeSelected($event)"
          @prizeUnselected="prizeUnselected($event)"
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
      prizesShown: false,
    };
  },
  methods: {
    ticketsAdded: function (ticketNumber) {
      this.currentTickets = ticketNumber;
      this.prizesShown = true;
    },
    prizeSelected: function (cost) {
      this.currentTickets = this.currentTickets - cost;
    },
    prizeUnselected: function (cost) {
      this.currentTickets = this.currentTickets + cost;
    },
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

#bottom-row {
  margin-bottom: 40px;
}

#ticket {
  background-image: url("./assets/ticket.png");
  background-size: contain;
  background-repeat: no-repeat;
  background-position: fixed;
  margin-top: 60px;
  width: 350px;
  height: 150px;
}

#ticket-counter {
  padding-top: 48px;
  font-weight: bold;
  font-size: 1.75rem;
  text-align: left;
  padding-left: 50px;
}

h1 {
  color: white;
  font-family: "Butterfly Kids", cursive;
  font-size: 6rem;
}

#riley {
  max-height: 275px;
}
</style>
