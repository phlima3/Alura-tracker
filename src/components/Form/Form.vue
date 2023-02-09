<template>
  <div class="box">
    <div class="columns">
      <div
        class="column is-8"
        role="form"
        aria-label="Formulário para criação de uma nova tarefa"
      >
        <input
          type="text"
          class="input"
          placeholder="Qual tarefa você deseja iniciar?"
          v-model="task"
        />
      </div>

      <div class="column">
        <Temporizator @time-is-finished="finishTask" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Temporizator from "../Temporizator/Temporizator.vue";

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Formulario",
  components: {
    Temporizator,
  },
  data() {
    return {
      task: "",
    };
  },
  methods: {
    finishTask(time: number): void {
      console.log(this.task, time);
      this.task = "";
    },
  },
});
</script>
