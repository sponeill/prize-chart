<template>
  <div>
    <b-card :title= title class="prize-card">
      <b-row>
        <b-col>
          <img :src="imgSrc" /><br />
        </b-col>
      </b-row>
      <b-row class="ticket-row">
        <b-col>
          {{ numberOfTickets }} Tickets!
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
    numberOfTickets: Number,
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
