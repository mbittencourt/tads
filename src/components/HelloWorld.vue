<template>
  <div class="hello">
    <h1>Cadastro de Usuario</h1>
    <p>
      Anhanguera TADS
    </p>
    <br />
     <p>
        Codigo: <input v-model="dto.codigo" placeholder="Codigo">
    </p>
    <p>
        Nome: <input v-model="dto.nome" placeholder="Nome">
    </p>
    <p>
        <button v-on:click="validaFormulario">Salvar</button>
        <button v-on:click="voltar">Voltar</button>
    </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data(){
    return {
      dto: {}
    }
  },
  
  methods: {
    validaFormulario: function () {
      if(this.dto.nome != null && this.dto.nome != undefined && this.dto.nome.length > 3){
        alert('Seja bem vindo: '+ this.dto.nome)
      }else{
        alert('Digite um nome válido.')
      }     
    },
    voltar: function () {  
      alert('Clicou no botão voltar.')
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
