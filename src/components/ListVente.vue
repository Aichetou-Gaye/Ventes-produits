<template>

  <table class="table table-bordered table-sm">
    <thead>
      <tr>
        <td>#</td>
        <td>Reference</td>
        <td>Désignation</td>
        <td>Quantité Vendue</td>
        <td>Prix de vente</td>
        <td>Montant</td>
      </tr>
    </thead>
    <tbody v-for="(produit, index) in produits" :key="index">
      <td>{{ index + 1 }}</td>
      <td>{{ produit.reference }}</td>
      <td>{{ produit.designation }}</td>
      <td>{{ produit.qtite }}</td>
      <td>{{ produit.prix }}</td>
      <td>{{ produit.qtite * produit.prix }}</td>
    </tbody>
    <tfoot>
      <tr>
        <td colspan="3" class="text-center">Total</td>
        <td>{{ total }}</td>
      </tr>
    </tfoot>
  </table>

</template>

<script setup>

// const props = defineProps({
//   produits : {
//     type : Array,

//   }
// })

</script>


<style scoped></style>
