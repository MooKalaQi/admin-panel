<template>
  <h1>Add Your New Card Information :</h1>
  <form @submit="onSubmit">
    <label for="Card-number">Card Number: </label>
    <input type="text" name="Card-number" v-model="cardNumber" />

    <label for="cvv2">CVV2: </label>
    <input type="text" name="cvv2" v-model="cvv2" />

    <label for="exp">Expiration Date: </label>
    <input type="text" form="exp" v-model="expDate" />

    <label for="balance">Card Balance: </label>
    <input type="text" name="balance" v-model="balance" />

    <div>
      <label>Saving</label>
      <input type="checkbox" name="saving" v-model="saving" />
    </div>

    <input type="submit" value="Submit" />
  </form>
</template>

<script>
export default {
  name: 'AddCard',
  data() {
    return {
      cardNumber: '',
      cvv2: '',
      expDate: '',
      balance: '',
      saving: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();

      if (!this.cardNumber || !this.cvv2 || !this.expDate) {
        alert('Please fill out all froms');
      }
      const newCard = {
        cardNumber: this.cardNumber,
        cvv2: this.cvv2,
        expDate: this.expDate,
        balance: this.balance,
        saving: this.saving,
      };
      this.$emit('add-card', newCard);
      (this.cardNumber = ''),
        (this.cvv2 = ''),
        (this.expDate = ''),
        (this.balance = ''),
        (this.saving = false);
    },
  },
};
</script>
<style>
form {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 5rem;
}
label {
  margin-top: 2rem;
  font-size: 1.3rem;
}
input {
  width: 75%;
  border: none;
  background: rgb(255, 255, 255);
  box-shadow: 1px 1px 5px 0px rgba(0, 0, 0, 0.233);
  height: 3rem;
  border-radius: 5px;
}
input[type='submit'] {
  background: teal;
  width: 50%;
  margin: auto;
  margin-top: 5rem;
  color: white;
  font-size: 1.5rem;
}
</style>
