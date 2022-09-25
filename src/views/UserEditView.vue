<template>
  <div>
    Usuário <br>

    <button @click="login()">
      Login
    </button>
  </div>
</template>

<script>
export default {
  name: "UserEdit",

  created() {
    // INFO SOBRE O OBJETO/ROTA ATUAL
    // console.log(this.$route)

    // FUNCIONALIDADES DO ROTEAMENTO
    // console.log(this.$router);
  },

  methods: {
    login() {
      this.$router.push('/about');
    }
  }
}
</script>

<style scoped>

</style>