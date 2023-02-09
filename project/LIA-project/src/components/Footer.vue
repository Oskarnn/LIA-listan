<script>
export default {
  data() {
    return {
      date: "2023-02-09",
    };
  },
};
</script>

<template>
  <div>
    <p>Skapad av Oskar Nygren</p>
    <p>{{ date }}</p>
  </div>
</template>

<style scoped>
div {
  background-color: rgba(0, 0, 0, 0.1);
  font-family: Roboto;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  margin-top: 10%;
  min-height: 10vh;
}
</style>
