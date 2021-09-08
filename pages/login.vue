<template>
  <div class="container">
    <div class="row">
      <div class="col mx-auto">
        <div class="card">
          Login
          <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 border border-blue-700 rounded" @click="login">
            Enter
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      form: {
        email: 'joseph2019@gmail.com',
        password: 'joseph',
      }
    }
  },
  methods: {
    login() {
      this.$auth.loginWith('laravelSanctum', {
        data: this.form
      })
      .then(response => console.log(response))
      .catch(error => alert(error))
    }
  }
}
</script>
