<template>
  <div>
    <b-container>
      <b-row class="mt-5">
        <b-col sm="12">
          <h2 class="text-center">To do list</h2>
        </b-col>
      </b-row>
      <b-row align-h="center">
        <b-col sm="6">
          <b-input-group>
            <b-input placeholder="Insira seu texto" v-model="novoItem" />
            <b-input-group-append>
              <b-button variant="primary" @click="adicionarItem"> Adicionar</b-button>
            </b-input-group-append>
          </b-input-group>
        </b-col>
      </b-row>
      <b-row align-h="center" class="mt-5">
        <b-col sm="6">
          <ul>
            <li v-for="(umIntem, index) in itens" :key="index">
              {{umIntem}}
              <b-button variant="danger" @click="removeItem(index)"> Deletar </b-button>
            </li>
          </ul>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>
<script>
export default {
  name: "ToDoList",
  data: function(){
    return {
      novoItem : "",
      itens : []
    }
  },
  methods:{
    adicionarItem : function(){
      this.itens.push(this.novoItem)
    },
    removeItem : function(index){
      const array = this.itens;
      this.itens = array.splice(index, 1)
    }
  }
}
</script>
<style>
  .text-center{
    text-align: center;
  }
</style>