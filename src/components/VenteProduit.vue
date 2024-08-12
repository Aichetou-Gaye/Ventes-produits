<template>
  <div class="form">

    <form @submit.prevent="onSubmit">
      <h1>Enregistrement de Produits</h1>
      <div class="row">
        <div class="label">
          <label for="input-1">Reference:</label>
          <input id="input-1" v-model="reference" type="text" placeholder="Entrez la référence du produit" required>
        </div>
        <div class="label">
          <label for="input-2">Désignation:</label>
          <input id="input-2" v-model="designation" type="text" placeholder="Entrez la désignation" required>
        </div>
      </div>
      <div class="row">
        <div class="label">
          <label for="input-3">Quantité Vendue:</label>
          <input id="input-3" v-model="qtite" type="number" placeholder="Entrez la quantité vendue du produit" required>
        </div>
        <div class="label">
          <label for="input-4">Prix de vente:</label>
          <input id="input-4" v-model="prix" type="number" placeholder="Entrez le prix du produit" required>
        </div>

      </div>

      <button type="submit">Enregistrer</button>
    </form>
    <table>
      <thead>
        <tr>
          <td>Reference</td>
          <td>Désignation</td>
          <td>Quantité Vendue</td>
          <td>Prix de vente</td>
        </tr>
      </thead>
      <tbody v-for="produit in produit" :key="produit.id">
        <td>{{ produit.r }}</td>
        <td>{{ produit.d }}</td>
        <td>{{ produit.q }}</td>
        <td>{{ produit.p }}</td>
      </tbody>
    </table>

  </div>

</template>

<script setup>
import { ref, reactive } from 'vue'

const produit = reactive([{
  id: Date.now(),
  r: "",
  d: "",
  q: "",
  p: ""
}
])
const reference = ref('')
const designation = ref('')
const qtite = ref('')
const prix = ref('')

function onSubmit() {
  try {
    if (!reference.value || !designation.value || !qtite.value || !prix.value) {
      throw new Error("Veuillez entrer des données valide")
    }
  } catch (e) {
    console.log(e.message)
  }
  produit.push({ r: reference.value, d: designation.value, q: qtite.value, p: prix.value })
  reference.value = ""
  designation.value = ""
  qtite.value = ""
  prix.value = ""
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
  width: 55%;
  margin: auto;
  font-family: "Montserrat Alternates", sans-serif;
}
label {
  font-size: 1em;
}
.row{
  display: flex;
  justify-content: space-between;
}
h1 {
  font-size: 1.2em;
  text-align: center;
  margin-bottom: 20px
}
input {
  border-radius: 5px;
  padding: 10px;
  margin: 5px 0px 20px 0px;
  border: none;
  font-family: "Montserrat Alternates", sans-serif;
  color: #000000;
  width: 60%;
  font-size: 0.9em;
}

input::placeholder {
  color: #000;
}

input:focus {
  background-color: #000000;
  color: #ffffff;
  outline: none;
}
.label {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
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
.form {
  display: flex;
  flex-direction: column;
}
thead {
  color: #ffffff;
  background-color: #228d5b;
  border: 1px solid #fff;
}

tbody {
  color: #000;
  background-color: #ffffff ;
  border: 1px solid #000;
  text-align: center;
}
</style>
