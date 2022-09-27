<script>
import HelloWorld from "./components/HelloWorld.vue";
import { ref, reactive } from "vue";

export default {
  name: "App",

  components: { HelloWorld },

  setup() {
    const user = reactive({
      first_name: 'Jon',
      last_name: 'Snow'
    });

    const admin = ref({
      first_name: 'Admin',
      last_name: 'Master'
    });

    let name = 'Lucas';

    const changeName = () => {
      name = 'Jon Sow';
      user.first_name = 'Sansa';
      admin.value.first_name = 'Ademir';
    };

    return {
      name,
      admin,
      user,
      changeName
    }
  }
}
</script>

<template>
  <header>
    {{ name }}
    <br><br>
    <h5>User</h5>
    {{ user.first_name }} {{ user.last_name }}
    <br><br>
    <h5>Admin</h5>
    {{ admin.first_name }} {{ admin.last_name }}
    <img
      @click = "changeName()"
      alt="Vue logo"
      class="logo"
      src="./assets/logo.svg"
      width="125"
      height="125"
    />

    <div class="wrapper">
      <HelloWorld msg="You did it!" />
    </div>
  </header>

  <main>
    <TheWelcome />
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
  /*header {*/
  /*  display: flex;*/
  /*  place-items: center;*/
  /*  padding-right: calc(var(--section-gap) / 2);*/
  /*}*/

  /*.logo {*/
  /*  margin: 0 2rem 0 0;*/
  /*}*/

  /*header .wrapper {*/
  /*  display: flex;*/
  /*  place-items: flex-start;*/
  /*  flex-wrap: wrap;*/
  /*}*/
}
</style>
