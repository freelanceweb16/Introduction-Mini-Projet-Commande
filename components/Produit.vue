<template>
  <!-- <div class="card" v-for="produit in produits" v-bind:key="produit.id"> -->
    <div class="card">
    <img :class="card - img - top" :src="image" :alt="nom">
    <div class="card-body">
      <h5 class="card-title">{{nom}}</h5>
      <p class="card-text">
        <i>{{description}}</i><br />
        <strong>{{prix}} &euro;</strong>
      </p>

      <button v-if="role == 'commander'" class="btn btn-primary" @click="$emit('commande', nom, prix, image, description)">Ajouter au panier</button>
    </div>
  </div>
</template>

<script scoped>
export default{
  name:'Produit',
  props:['nom','prix','description','image', 'role'],
}
</script>