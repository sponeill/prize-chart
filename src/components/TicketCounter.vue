<template>
  <div>
    <b-card class="ticket-window">
      <b-row>
        <b-col class="input-col">
          <b-form-input
            v-model="ticketNumber"
            placeholder="How many tickets do you have?"
            class="ticket-input"
            type ="number"
          ></b-form-input>
          <b-btn class="ticket-btn" v-on:click="showPrizes"
            >Show Me My Prizes!</b-btn
          >
        </b-col>
      </b-row>
    </b-card>
  </div>
</template>

<script>
export default {
  name: "TicketCounter",
  props: {},
  data: function () {
      return {
        ticketNumber: '',
      };
  },
  methods: {
    showPrizes: function () {
      console.log("Button clicked:" + this.ticketNumber);
      this.$emit('ticketsAdded', this.ticketNumber);
    },
  },
};
</script>

<style scoped>
.ticket-window {
  border-radius: 15px;
  display: inherit;
  margin-top: 100px;
}

.input-col {
  display: inherit;
}

.ticket-input {
  margin-left: 25px;
  max-width: 60%;
}

.ticket-btn {
  background-color: purple;
  margin-left: 15px;
}
</style>
