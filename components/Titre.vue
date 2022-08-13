<template>
<div>

  <h1>{{titre}}</h1>
  <h2>{{sousTitre}}</h2>

</div>
</template>

<style scoped>
h1{
  font-size: 2.5rem;
  margin-bottom: 1rem;
  text-align:center;
}
h2{
  font-size: 1.5rem;
  margin-bottom: 1rem;
  text-align:center;
  font-weight: 100;
}
</style>

<script scoped>
export default{
  name:'Titre',
  props:['titre', 'sousTitre'],
}
</script>