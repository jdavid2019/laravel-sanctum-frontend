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
    let session_token = '14|waTVEDk1nHAgqCqVqgeIeVQQLHyaCXjmsyAu09yM';
    axios.get('http://127.0.0.1:8000/api/user/all', {
      headers: {
        'content-type' : 'application/json',
        'Authorization': `Bearer ${session_token}`,
      }
    })
      .then(albumResponse=>{
        console.log(albumResponse.data)
      })
    //console.log(this.$route)
    //let albumId = this.$route.params.id;
    //console.log(albumId)
  }
}
</script>

