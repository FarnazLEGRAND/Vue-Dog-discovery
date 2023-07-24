<script set up lang="ts" setup>
const names=ref(['jon','Far','max'])
const newName=ref('');
function addName(): void{
  names.value.push(newName.value)
}
</script>


<template>
  <div>
<input class="form-control" type="text" v-model="newName" placeholder="type your name">
<button @click="addName()"  class="btn btn-warning">Add</button>
    <ul id="array-rendering" class="list-group">
      <li class="list-group-item" v-for="item of names">
        {{ item }}
      </li>
    </ul>
  </div>
</template>

<style scoped></style>
