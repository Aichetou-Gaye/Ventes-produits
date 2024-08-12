<template>
  <div class="form">

    <form @submit="onSubmit" @reset="onReset">
      <h1>Enregistrement de Produits
      </h1>
      <label for="input-1">Reference:</label>
      <input id="input-1" v-model="reference" type="text" placeholder="Entrez la référence du produit" required>

      <label for="input-2">Désignation:</label>
      <input id="input-2" v-model="designation" placeholder="Entrez la désignation" required>

      <label for="input-3">Quantité Vendue:</label>
      <input id="input-3" v-model="qtite" placeholder="Entrez la quantité vendue du produit" required>

      <label for="input-4">Prix de vente:</label>
      <input id="input-4" v-model="prix" placeholder="Entrez le prix du produit" required>

      <button type="submit">Enregistrer</button>
      <button type="reset">Supprimer</button>
    </form>
  </div>

</template>

<script setup>
import { ref } from 'vue'
const reference = ref('')
const designation = ref('')
const qtite = ref('')
const prix = ref('')

function onSubmit() {

}

function onReset() {

}
</script>


<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Montserrat+Alternates:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&family=Montserrat:ital,wght@0,100..900;1,100..900&family=Poppins:ital,wght@0,100;0,200;0,300;0,400;0,500;0,600;0,700;0,800;0,900;1,100;1,200;1,300;1,400;1,500;1,600;1,700;1,800;1,900&display=swap');

form {
  display: flex;
  flex-direction: column;
  background-color: #055e34;
  color: #FFFFFF;
  padding: 30px 60px;
  border-radius: 10px;
  opacity: 0.95;
  width: 45%;
  margin: auto;
  font-family: "Montserrat Alternates", sans-serif;
}

label {
  font-size: 1em;
}
h1 {
  font-size: 1.2em;
  text-align: center;
}
input {
  border-radius: 5px;
  padding: 10px;
  margin: 5px 0px 20px 0px;
  border: none;
  font-family: "Montserrat Alternates", sans-serif;
  color: #000000;
}

input::placeholder {
  color: #000;
}

input:focus {
  background-color: #000000;
  color: #ffffff;
  outline: none;
}

button {
  border-radius: 5px;
  padding: 10px;
  margin: 5px 0px 20px 0px;
  border: none;
  color: #ffffff;
  background-color: #228d5b;
  font-weight: bolder;
  font-size: 1em;
  font-family: "Montserrat Alternates", sans-serif;
  cursor: pointer;
}

button:hover {
  color: #228d5b;
  background-color: #ffffff;
}
</style>
