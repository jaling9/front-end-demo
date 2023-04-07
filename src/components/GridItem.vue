<template>
  <Card :class="cardClass">
    <template #title>
      {{ title }}
    </template>
    <template #content>
      {{ content }}
    </template>
  </Card>
</template>

<script>
import { Card } from "primevue/card";

export default {
  components: {
    Card,
  },
  props: {
    title: {
      type: String,
      default: "Grid Item",
    },
    content: {
      type: String,
      default: "This is a grid item.",
    },
    cardClass: {
      type: String,
      default: "",
    },
  },
};
</script>
