<script lang="ts" setup>
import { Dog } from "../entities";
// @Input ({required:true}) touye angular defineProps<{}()
// dog: Dog;
defineProps<{
  dog: Dog
}>()
</script>

<template>
  <div>
    Component: dog-item
  </div>
</template>

<style scoped></style>
