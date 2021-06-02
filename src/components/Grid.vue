<template>
  <div class="hello">

    

    <p>

          <button v-on:click="populaTabela">Popula Tabela</button>

          <button v-on:click="populaTabelaPorAPI">Popula Tabela API</button>

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

import axios from 'axios'

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
            key: 'id',
            sortable: true
          },
          {
            key: 'name',
            sortable: true
          },
          {
            key: 'email',
            sortable: true
          }
      ],
      dto: [
            
          ]
    }
  },
  
  methods: {
    
    populaTabelaPorAPI(){
      
      axios
      .get('https://jsonplaceholder.typicode.com/users')
      .then(response => {
        
        this.dto = response.data;
        
        
      });
    },
    populaTabela(){
      this.dto = [
            {
              "name": "Henrique",
              "id": 58,
              "email": "email58@gmail.com"
            },
            {
              "name": "Charles",
              "id": 39,
              "email": "email39@gmail.com"
            },
            {
              "name": "Keven",
              "id": 47,
              "email": "email47@gmail.com"
            },
            {
              "name": "Messias",
              "id": 18,
              "email": "email18@gmail.com"
            },
            {
              "name": "Gustavo",
              "id": 57,
              "email": "email57@gmail.com"
            },
            {
              "name": "Carlos Augusto",
              "id": 48,
              "email": "email48@gmail.com"
            },
            {
              "name": "Natalia",
              "id": 18,
              "email": "email18@gmail.com"
            }
      ];
    }
  },
  created(){
   axios
      .get('https://jsonplaceholder.typicode.com/users')
      .then(response => {
        
       
        this.dto = response.data;
        
        
      });
  },
  computed: {
      rows() {
        return this.dto.length
      }
    }
}
</script>
