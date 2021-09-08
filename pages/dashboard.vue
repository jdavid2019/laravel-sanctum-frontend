<template>
  <div class="container">
    <div class="row">
      <div class="col mx-auto">
        <div class="card">
          Welcome  {{ $auth.user.name  }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import methods from "methods";
import axios from 'axios';
export default {
  // si quiero que ha esta página no le afecte la autenticacion
 // auth: false
  auth: true,
  // si quiero protegerlo de manera autenticada middleware: "auth" pero tengo que comentar  router: {
 // middleware: ["auth"] en nuxt.config.js y aqui coloco middleware: "auth"
//},
  methods: {

  },
  mounted() {
    axios.get('http://127.0.0.1:8000/api/v1/user/all')
      .then(albumResponse=>{
        console.log(albumResponse.data)
      })
    //console.log(this.$route)
    //let albumId = this.$route.params.id;
    //console.log(albumId)
  }
}
</script>

