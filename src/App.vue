<template>
  <div>
    Hello Vue
  </div>

  <br>

  <AppButton
    data-vue="Jon"
    variant="danger"
    @update="getUpdate"
  >
    Save
    <template #icon>Icon</template>
  </AppButton>

</template>

<script>
import AppButton from "@/components/AppButton.vue";

export default {
  name: "App",

  components: { AppButton },

  setup() {
    const getUpdate = (data) => {
      console.log('getUpdate', data);
    };

    return {
      getUpdate
    }
  }
}
</script>

<style scoped>

</style>
