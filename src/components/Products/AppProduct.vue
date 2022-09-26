<template>
  <div class="card">

    {{ product.name }} - R$ {{ product.price }}

    <button @click="addProduct()">
      Adicionar
    </button>

    <button @click="removeProduct()">
      Remover
    </button>
  </div>
</template>

<script>
export default {
  name: "AppProduct",

  props: {
    product: Object
  },

  methods: {
    addProduct() {
      this.$store.commit('addProduct', this.product);
    },

    removeProduct() {
      this.$store.commit('removeProduct', this.product);
    }
  }
}
</script>

<style scoped>
  .card {
    background: bisque;
    padding: 6px;
    margin-bottom: 5px;
    border-radius: 5px;
  }
</style>