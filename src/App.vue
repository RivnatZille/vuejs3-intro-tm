<script>
// import HelloWorld from "./components/HelloWorld.vue";
import AppHook from "./components/AppHook.vue";
import { ref, computed, watch } from "vue";

export default {
  name: "App",

  components: { AppHook },

  setup() {
    const user = ref({
      first_name: 'Jon',
      last_name: 'Snow'
    });

    const fullName = computed(() => `${user.value.first_name} ${user.value.last_name}`);

    const showAppHook = ref(true);

    watch(user, () => {
      console.log('Testando o Watch');
    }, {
      deep: true
    });

    return {
      user,
      fullName,
      showAppHook
    }
  }
}
</script>

<template>
  <div>
    <AppHook v-if="showAppHook"/>
    <button @click="showAppHook = ! showAppHook">Toggle</button>
  </div>

  <div>
    <h5>User</h5>
    <p>{{ user.first_name }} {{ user.last_name }}</p>
  </div>
  <br><br>
  <div>
    <h5>Full Name</h5>
    <p>{{ fullName }}</p>
    <br>
    <button @click="user.first_name = 'Sansa'">Atualizar</button>
  </div>


<!--    <img-->
<!--      @click = "changeName()"-->
<!--      alt="Vue logo"-->
<!--      class="logo"-->
<!--      src="./assets/logo.svg"-->
<!--      width="125"-->
<!--      height="125"-->
<!--    />-->

<!--    <div class="wrapper">-->
<!--      <HelloWorld msg="You did it!" />-->
<!--    </div>-->

</template>

<style scoped>

</style>
