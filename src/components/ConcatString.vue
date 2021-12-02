<template>
  <b-container class="mt-5">
    <b-row align-h="center" >
      <b-col  sm="6">
        <b-form-group label="Nome :">
          <b-form-input placeholder="Nome" v-model="nome" />
        </b-form-group>
        <b-form-group class="mt-3" label="Sobrenome :">
          <b-form-input placeholder="Sobrenome" v-model="sobrenome" />
        </b-form-group>
      </b-col>
    </b-row>
    <b-row class="justify-content-sm-center">
      <b-col sm='2' align-self="center" class="mt-3">
        <b-button variant="primary" class="center-button" @click="concatena">Concater</b-button>
      </b-col>
    </b-row>
    <b-row class="mt-3">
      <p>{{resultado}}</p>
    </b-row>
  </b-container>
</template>

<script>
export default {
  name: "ConcatString",
  data: function () {
    return {
      nome: "",
      sobrenome: "",
      resultado : ""
    };
  },
  methods : {
    concatena : function(){
      this.resultado = this.nome + " " + this.sobrenome
    }
  }
};
</script>
<style>
.box-content {
  padding-top: 100px;
}

.center-button{
  margin: auto;
  display: block!important;
}
</style>