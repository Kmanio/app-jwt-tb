<template>
  <div class="about">
    <h1>Ruta protegida</h1>
    {{token}}
  </div>
</template>

<script>
import {mapState} from 'vuex'
export default{
  computed:{
    ...mapState(['token'])
  },
  methods:{
    async datosProtegidos(){
      try {
        const res = await fetch('https://api-jwt-yt-tutorial.herokuapp.com/api/admin',{
          headers:{
            'Content-Type': 'application/json',
            'auth-token': this.token
          },
        })
        const datDB = await res.json();
        console.log(datDB);
      } catch (error) {
        console.log(error);
      }
    }
  },
  created(){
    this.datosProtegidos();
  }
}
</script>