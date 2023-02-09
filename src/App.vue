<template>
  <main class="columns is-gapless is-multiline">
    <div class="column is-one-quarter">
      <SideBar />
    </div>
    <div class="column is-three-quarter">
      <Formulario />
    </div>
  </main>
</template>

<script lang="ts">
import { defineComponent } from "vue";

import SideBar from "./components/Sidebar/Sidebar.vue";
import Formulario from "./components/Form/Form.vue";

export default defineComponent({
  name: "App",
  components: {
    SideBar,
    Formulario,
  },
});
</script>

<style></style>
