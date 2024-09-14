<script setup>

import {ref} from 'vue'

const count= ref(0)

</script>

<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-3 text-center">
        <h1>Bootstrap</h1>
        <button class="btn btn-danger" @click="count++">{{ count }}</button>
      </div>
    </div>
  </div>


</template>

<style scoped>

</style>
