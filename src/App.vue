<script>
import AppProducts from "./components/Products/AppProducts.vue";

export default {
  name: "App",

  components: {
    AppProducts,
  },

  data() {
    return {};
  },

  methods: {
    updateUser() {
      const newUser = {
        first_name: "Lucas",
        last_name: "Zille",
        email: "lucas@zille.com",
      };

      this.$store.commit('storeUser', newUser);
    }
  },
};
</script>

<template>
  <main>
    <AppProducts></AppProducts>

    <br><br>

    R$ {{ $store.getters.total }}

    <br>

    {{ $store.state.cart }}

    <br><br>

    <button
        @click="updateUser()"
    >Atualizar perfil
    </button>
  </main>
</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>
