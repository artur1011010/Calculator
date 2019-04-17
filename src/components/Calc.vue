<template>
  <div class="calculator">
    <div class="disp">225252</div>
    <div>C</div>
    <div>+/-</div>
    <div>%</div>
    <div>/</div>
    <div>7</div>
    <div>8</div>
    <div>9</div>
    <div>x</div>
    <div>4</div>
    <div>5</div>
    <div>6</div>
    <div>-</div>
    <div>1</div>
    <div>2</div>
    <div>3</div>
    <div>+</div>
    <div>+/-</div>
    <div>0</div>
    <div>,</div>
    <div>=</div>
  </div>
</template>

<script>

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator{
  font-size: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  background-color: rgb(226, 223, 223);
}
.calculator div{
  border: 3px solid rgb(187, 185, 185);
  padding-top: 20px;
  padding-bottom: 20px;
}
.disp{
  grid-column: 1/5;
  background-color: rgb(182, 182, 182);
}
</style>
