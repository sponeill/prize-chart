<template>
  <div>
    <b-card :title= title class="prize-card animate__animated animate__fadeInUp animate__delay-2s">
      <b-row>
        <b-col>
          <img :src="imgSrc" /><br />
        </b-col>
      </b-row>
      <b-row class="ticket-row">
        <b-col>
          {{ ticketCost }} Tickets!
        </b-col>
      </b-row>
      Current Tickets: {{ currentTickets }}
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
  },
};
</script>

<style scoped>

.prize-card {
  max-width: 20rem;
  border-radius: 15px;
  margin-left: auto;
  margin-right: auto;
}

.ticket-row {
  margin-top: 15px;
  font-weight: bold;
}

</style>
