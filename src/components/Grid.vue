<template>
  <div class="hello">
    <p>
          <b-table 
            striped hover 
            :items="dto"  
            :fields="campos"
            :per-page="registroPorPagina"
            :current-page="paginaAtual"
          />


          <b-pagination
            v-model="paginaAtual"
            :total-rows="rows"
            :per-page="registroPorPagina"
            aria-controls="my-table"
          ></b-pagination>
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
      registroPorPagina: 3,
      paginaAtual: 1,

      campos: [
          {
            key: 'nome',
            sortable: true
          },
          {
            key: 'idade',
            sortable: true
          }
      ],
      dto: [
            {
              "nome": "Henrique",
              "idade": 58
            },
            {
              "nome": "Charles",
              "idade": 39
            },
            {
              "nome": "Keven",
              "idade": 47
            },
            {
              "nome": "Messias",
              "idade": 18
            },
            {
              "nome": "Gustavo",
              "idade": 57
            },
            {
              "nome": "Carlos Augusto",
              "idade": 48
            },
            {
              "nome": "Natalia",
              "idade": 18
            }
          ]
    }
  },
  
  methods: {
    
  },

  computed: {
      rows() {
        return this.dto.length
      }
    }
}
</script>
