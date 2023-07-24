<script lang="ts" setup>

const first=ref('test');
function changeFirst(){
  first.value='autre chose'
}
</script>

<template>
  <div>
    {{first}}
    <button @click="changeFirst">click!</button>
  </div>
</template>

<style scoped></style>
