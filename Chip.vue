<template>
  <v-chip :color="getColor()" :text-color="getTextColor()">
    <slot></slot>
  </v-chip>
</template>

<script setup lang="ts">
const props = defineProps<{
  type: "error" | "info" | "success" | "warning" | undefined;
}>();

function getColor() {
  if (props.type) {
    switch (props.type) {
      case "error":
        return "red";
      case "info":
        return "primary";
      case "success":
        return "green";
      case "warning":
        return "orange";
    }
  }
}

function getTextColor() {
  return props.type ? "white" : null;
}
</script>
