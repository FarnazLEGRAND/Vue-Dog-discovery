<script lang="ts" setup>
import { Dog } from 'entities';
//data . reflesh  pour relance,... il fait requet ver backend avec use fetch
const { data, refresh } = useFetch<Dog[]>('http://localhost:8000/api/dog');

// function addDog (dog:Dog) {
// console.log(dog);
// }

async function addDog(dog: Dog) {
  await $fetch('http://localhost:8000/api/dog', {
    method: 'POST',
    body: dog
  });
  refresh();
}
</script>

<template>
  <div>

    <FormDog @submitDog="addDog($event)" />

    <!-- <p v-for="item of data">{{ item.name }}</p> -->
    <DogItem v-for="item of data" :dog="item" />
  </div>
</template>

<style scoped></style>
