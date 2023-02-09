<template>
  <section>
    <strong>{{ timeDecorrido }}</strong>
  </section>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  // eslint-disable-next-line vue/multi-word-component-names
  name: "Chronometer",
  props: {
    time: {
      type: Number,
      default: 0,
    },
  },
  computed: {
    timeDecorrido(): string {
      return new Date(this.time * 1000).toISOString().substr(11, 8);
    },
  },
});
</script>
