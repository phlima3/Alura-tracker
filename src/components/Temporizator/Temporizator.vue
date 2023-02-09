<template>
  <section
    class="is-flex is-align-items-center is-justify-content-space-between"
  >
    <Chronometer :time="time" />
    <Button
      @clicado="start"
      icone="fas fa-play"
      texto="play"
      :desabilitado="isActive"
    />
    <Button
      @clicado="stop"
      icone="fas fa-stop"
      texto="stop"
      :desabilitado="!isActive"
    />
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Chronometer from "../Chronometer/Chronometer.vue";
import Button from "../TemporizatorButtons/Button.vue";

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Temporizator",
  emits: ["timeIsFinished"],
  components: {
    Chronometer,
    Button,
  },
  data() {
    return {
      time: 0,
      chronometer: 0,
      isActive: false,
    };
  },
  computed: {
    timeDecorrido(): string {
      return new Date(this.time * 1000).toISOString().substr(11, 8);
    },
  },
  methods: {
    start() {
      this.isActive = true;
      this.chronometer = setInterval(() => {
        this.time++;
      }, 1000);
    },
    stop() {
      this.isActive = false;
      clearInterval(this.chronometer);
      this.$emit("timeIsFinished", this.time);
      this.time = 0;
    },
  },
});
</script>
