<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png"> -->
    <h1>Login </h1>

<form @submit.prevent="login(usuario)">
  <input type="email" placeholder="email"  v-model="usuario.email" >
  <input type="password" placeholder="pass" v-model="usuario.password" >
  <button type="submit">Acceder</button>
</form>
{{usuario}}
  </div>
</template>

<script>
// @ is an alias to /src
import{mapActions} from 'vuex'

export default {
  data(){
    return {
      usuario:{
        email:'Luis@rada.com',
        password:'123456'
      }
    }
  },
methods:{
  ...mapActions(['login'])
}

}
</script>
