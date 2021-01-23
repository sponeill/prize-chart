<template>
  <div>
   <b-card
      v-if="hasEnoughTickets"
      v-on:click="prizeClicked"
      :title="title"
      class="prize-card animate__animated animate__flipInY animate__delay-1s"
      v-bind:class="{ selected: selected }"
    >
      <b-row>
        <b-col> <img :src="imgSrc" /><br /> </b-col>
      </b-row>
      <b-row class="ticket-row text-success">
        <b-col> {{ ticketCost }} Tickets! </b-col>
      </b-row>
    </b-card>
    <b-card
      v-if="!hasEnoughTickets && prizesShown"
      :title="title"
      class="prize-card prize-card-disabled animate__animated animate__flipInY animate__delay-1s"
    >
      <b-row>
        <b-col> <img :src="imgSrc" /><br /> </b-col>
      </b-row>
      <b-row class="ticket-row">
        <b-col class="text-danger text-bold">
          You Need {{ ticketCost - currentTickets }} More Tickets!
        </b-col>
      </b-row>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "Prize",
  props: {
    title: String,
    imgSrc: String,
    ticketCost: Number,
    currentTickets: Number,
    url: String,
    prizesShown: Boolean
  },
  data: function () {
    return {
      selected: false,
    };
  },
  methods: {
    prizeClicked: function () {
      if (!this.selected) {
        this.selected = true;
        this.$emit("prizeSelected", this.ticketCost);
      } else {
        this.selected = false;
        this.$emit("prizeUnselected", this.ticketCost);
      }
    },
  },
  computed: {
    hasEnoughTickets: function () {
      return this.currentTickets >= this.ticketCost || this.selected;
    }
  },
};
</script>

<style scoped>
.prize-card {
  max-width: 20rem;
  border-radius: 15px;
  margin-left: auto;
  margin-right: auto;
  margin-top: 20px;
}

.selected {
  background-color: lightgreen;
}

.not-selected {
  background-color: white;
}

.card-title {
  color: purple;
  font-weight: bolder;
}

.prize-card-disabled {
  background-color: lightgray;
}

.ticket-row {
  margin-top: 15px;
  font-weight: bold;
}
</style>
