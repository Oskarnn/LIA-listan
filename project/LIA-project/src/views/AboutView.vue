<script setup>
import DataForm from '../components/DataForm.vue'
</script>

<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <div class="form">
    <DataForm/>
  </div>
</template>

<style scoped>
div{
  margin-top: 70px;
}
@media (min-width: 1024px) {
  .about {
    min-height: 100vh;
    display: flex;
    align-items: center;
  }
}
</style>
