<template>
  <div class="hello">
    <h1>Login de Usuario</h1>
    <p>
      Anhanguera TADS
    </p>
    <br />
    <p>
        Login: <input v-model="loginDTO.login" placeholder="Login">
    </p>
    <p>
        Senha: <input v-model="loginDTO.senha" placeholder="Senha" type="password">
    </p>
    <p>
        <button v-on:click="enviaDados">Login</button>
    </p>
  </div>
</template>

<script>



import router from '../router'


export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },

  data(){
    return {
      loginDTO: {}
    }
  },
  
  methods: {
    enviaDados(){
      
        if(this.loginDTO.login == 'user' && this.loginDTO.senha == 'user'){
          localStorage.setItem('user', "usuarioOk");
          router.push("/grid")
        }else{
          alert('Usuario e/ou senha invalida.');
        }
    },
    
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
