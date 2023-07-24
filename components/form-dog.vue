<script lang="ts" setup>
import { Dog } from "../entities";

// const emit = defineEmits([]);
const emit = defineEmits<{
(e: 'submitDog', dog: Dog): void
}>();

const dog = ref<Dog>({
  name:'',
  breed:'',
  birthdate:''
});


function handlesubmit(): void {
  // console.log(dog.value);
  emit('submitDog',dog.value)
}

</script>

<template>
  <div class="container">
    <form @submit.prevent="handlesubmit()">
      <label for="name">Name</label>
      <input class="form-control" type="text" name="name" id="name" v-model="dog.name" > 
      <label for="breed">Breed</label>
      <input class="form-control"  type="text" name="breed" id="breed" v-model="dog.breed" > 
      <label for="birthdate">Birthdate</label>
      <input class="form-control"  type="date" name="birthdate" id="birthdate" v-model="dog.birthdate">
       <button class="btn btn-primary">submit</button>
    </form>
  </div>
</template>

<style scoped></style>
