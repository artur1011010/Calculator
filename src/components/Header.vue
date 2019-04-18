<template>
  <div class="grid-header">
    <img src="../assets/logo.png">
    <h1>Welcome to my first Vue App</h1>
  </div>
</template>
<script>
</script>
<style>
.grid-header {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  padding: 0 10vw;
}
h1 {
  padding-top: 7vh;
  grid-column: 2/4;
  font-size: 39px;
  color:#C0B283;
}
</style>


