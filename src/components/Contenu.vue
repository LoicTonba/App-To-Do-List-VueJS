<template>
  <div class="container mt-5">

    
    <form>
      <div class="form-group mt-2">
        <h1>Rentrez vos choses à faire.</h1>
        <label for="action">Action</label>
        <input v-model="formData.tache" type="text" id="action" class="form-control mt-2">

        <button v-on:click.prevent="creationItem" class="btn btn-primary mt-2 mb-3">Créer une tache</button>
      </div>
      
    </form>

    <ul>
      <li v-bind:key="index" v-for="(tache, index) in tableauTaches">
        <item v-bind:id="index" :tache="tache" :suppression="suppression"></item>
      </li>
    </ul>
    
    <p class="text-center">copyright 2024 TONBA LOIC</p>
  </div>
</template>

<script>
import Item from './Item'
export default {
  name: 'HContenu',
  data: function(){
    return {
      formData: {
        tache: ''
      },
      tableauTaches: ['JavaScript','Vue','Python','React']
  }
},
 methods: {
    creationItem: function(){
      this.tableauTaches.push(this.formData.tache)
      this.formData.tache =''
    },
    suppression: function(e){
      //console.log(e.target.parentNode.id)
      this.tableauTaches.splice(e.target.parentNode.id, 1)
    }
 },
 
  components: {
    'item':Item
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1{
    margin-top: 100px!important;
  }

  ul{
    list-style-type: none;
    padding: 0;
  }
 
</style>
