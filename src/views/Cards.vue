<template>
  <div class="dashboard_header d-flex flex-row justify-content-between p-5">
    <h1>Cards</h1>
    <div class="d-flex flex-row align-items-center">
      <form class="d-flex flex-row">
        <button class="h-100">
          <i class="fa-solid fa-magnifying-glass fs-3"></i>
        </button>
        <input class="h-100" type="text" />
      </form>
      <button><i class="fa-solid fa-bell fs-3"></i></button>
    </div>
  </div>

  <div class="col-6 d-flex flex-column">
    <h1>Your Cards</h1>
    <div
      class="card_information w-50 d-flex flex-column align-items-center m-auto mt-5"
      v-for="card in cards"
      :key="card['card number']"
      :class="[card.saving ? 'saving_card':'']"
      >
      <p class="p-5 fs-2">{{ card.cardNumber}}</p>
      <div class="d-flex flex-row justify-content-between">
        <p class="p-3 fs-4">cvv2: {{ card.cvv2 }}</p>
        <p class="p-3 fs-4">ExpDate:{{ card.expDate }}</p>
      </div>
    </div>
    
    <button class="btn" @click="ShowAddCard()">Add Card</button>
    <div v-if="showAddCard" class="mt-5">
      <AddCard @add-card="addCard" />

    </div>
  </div>
</template>

<script>
import sourceData from '../data.json';
import AddCard from '../components/AddCard.vue';
export default {
  data() {
    return {
      cards: sourceData.cards,
      showAddCard:false
    };
  },
  components: {
    AddCard,
  },
  methods: {
    addCard(newCard) {
      this.cards= [...this.cards, newCard]
      this.cards.push(newCard);
      localStorage.setItem("cards", JSON.stringify(this.cards))
      console.log(this.cards)

    },
    ShowAddCard(){
      this.showAddCard = !this.showAddCard
    }
  },
};
</script>
<style scoped>
.btn {
  margin: auto;
  margin-top: 3rem;
  background-color: rgb(233, 106, 15);
  color: white;
  width: 10rem;
}
.btn:hover {
  transform: scale(1.1);
  transition: 0.7s;

  box-shadow: -1px 0px 2px 2px rgba(16, 16, 16, 0.157);
}
form {
  display: flex;
  width: 10rem;
  margin: 0 5rem;
  height: 3rem;
  border-radius: 5px;
}
form > * {
  background: #e2e2e2;
  border: none;
}
i {
  background: none;
  color: #000;
}
button {
  background: #e2e2e2;
  border: none;
  height: 3rem;
  width: 3rem;
}
.card_information {
  background-image: linear-gradient(
    90deg,
    teal,
    rgba(47, 15, 177, 0.446)
  ) !important;
  color: white;
  border-radius: 15px;
}
.saving_card{
  background-image: linear-gradient(90deg, rgb(231, 45, 45) , rgb(255, 188, 62))!important;
}
.card_information > * {
  background: none;
}
.card_information > div > * {
  background: none;
}
.card_information-cvv,
.card_information-exp {
  font-size: 1.5rem;
}
</style>
