<template>
<div>
    <header>
      <div class="container">
        <NuxtLogo />
        <Titre v-bind:key="1" v-bind:titre=titre v-bind:sousTitre=sousTitre />
        <Navigation />
      </div>
    </header>
    <main>
      <h2>Produit à la carte</h2>
      <div class="productList">
        <Produit v-for="produit in produits" v-bind:key="produit.id" v-bind:nom="produit.nom" v-bind:prix="produit.prix" v-bind:description="produit.description" v-bind:image="produit.image" v-bind:role="'commander'" v-on:commande="ajouterProduit"/>
      </div>


      <h2>Produit les plus commander</h2>

      <!-- <h2>Mon Panier</h2>
      <Produit v-for="commande in commandes" v-bind:key="commande.id" v-bind:nom="commande.nom" v-bind:prix="commande.prix" v-bind:role="'affichage'" v-bind:description="commande.description" v-bind:image="commande.image"/> -->
      
    </main>
</div>
</template>

<script>
import NuxtLogo from '@/components/NuxtLogo.vue';
import Navigation from '@/components/Navigation.vue';
import Produit from '@/components/Produit.vue';
import Titre from '@/components/Titre.vue';

export default {
  name: 'commande',
  components: {
    NuxtLogo,
    Navigation,
    Produit,
    Titre,
  },
  data() {
    return {
      titre : 'Commander',
      sousTitre : 'Vous pouvez nous contacter pour commander directement au 06.00.00.00.00', 
      produits: [
        {id: 1, nom: 'Pizza',prix: 10,description: 'Description du produit 1',image: 'https://picsum.photos/200/300/?random'},
        {id: 2, nom: 'Frites',prix: 20,description: 'Description du produit 2',image: 'https://picsum.photos/200/300/?random'},
        {id: 3,nom: 'Hamburger',prix: 30,description: 'Description du produit 3',image: 'https://picsum.photos/200/300/?random' },
        {id: 4,nom: 'Salade',prix: 40,description: 'Description du produit 4',image: 'https://picsum.photos/200/300/?random' },
        {id: 5,nom: 'Biere',prix: 50,description: 'Description du produit 5',image: 'https://picsum.photos/200/300/?random' },
        {id: 6,nom: 'Coca',prix: 60,description: 'Description du produit 6',image: 'https://picsum.photos/200/300/?random' },
        {id: 7,nom: 'Eau',prix: 70,description: 'Description du produit 7',image: 'https://picsum.photos/200/300/?random' },
        {id: 8,nom: 'CheeseBurger',prix: 80,description: 'Description du produit 8',image: 'https://picsum.photos/200/300/?random' },
        {id: 9,nom: 'Patatoes',prix: 90,description: 'Description du produit 9',image: 'https://picsum.photos/200/300/?random' },
        {id: 10,nom: 'Fanta',prix: 100,description: 'Description du produit 10',image: 'https://picsum.photos/200/300/?random' },
      ],
      commandes: [],
    }
  },
  methods: {
    ajouterProduit(nom, prix, image, description) {
      this.commandes.push({
        id: this.commandes.length + 1,
        nom: nom,
        prix: prix,
        description: description,
        image: image,
      });
    }
  }
}
</script>

<style scoped>
header > div > h1.h1{
  font-size: 2.5rem;
  margin-bottom: 1rem;
  text-align:center;
}

.card{
  margin-bottom: 1rem;
}

main{
  padding: 2em 8em 2em 8em;
}

.productList{
  display: inline-flex;
  gap: 1em;
  flex-direction: row;
  flex-wrap: wrap;
}

.card > img{
  width: 100%;
  height: 200px;
  object-fit: cover;
  object-position: center;
}

</style>

