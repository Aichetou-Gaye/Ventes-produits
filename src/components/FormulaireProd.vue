<template>
  <form class="row gy-2 gx-3 align-items-center" @submit="onSubmit">
    <div class="col-sm-3">
      <label for="ref">Reference</label>
      <input type="text" class="form-control" id="ref">
    </div>
    <div class="col-auto">
      <label for="desg">Designation</label>
      <input type="text" class="form-control" id="desg">
    </div>
    <div class="col-auto">
      <label for="qtite">Quantité</label>
      <input type="number" class="form-control" id="qtite">
    </div>
    <div class="col-auto">
      <label for="prix">Prix</label>
      <input type="number" class="form-control" id="prix">
    </div>

    <div class="col-auto">
      <button type="submit" class="btn btn-primary">Enregistrer</button>
    </div>
  </form>
</template>

<script setup>
import { ref } from 'vue'

const reference = ref('')
const designation = ref('')
const qtite = ref(1)
const prix = ref(0)

function onSubmit() {
  try {
    if (!reference.value || !designation.value || !qtite.value || !prix.value) {
      throw new Error("Veuillez entrer des données valide")
    }
  } catch (e) {
    console.log(e.message)
  }
  reference.value = ""
  designation.value = ""
  qtite.value = ""
  prix.value = ""
}

</script>
