<template>
  <div class="calculator">
    <div class="disp">{{current || '0'}}</div>
    <div @click="clear" class="btn operator">C</div>
    <div @click="sign" class="btn operator">+/-</div>
    <div @click="perc" class="btn operator">%</div>
    <div @click="division" class="btn operator">/</div>
    <div @click="append('7')" class="btn">7</div>
    <div @click="append('8')" class="btn">8</div>
    <div @click="append('9')" class="btn">9</div>
    <div @click="multiplication" class="btn operator">x</div>
    <div @click="append('4')" class="btn">4</div>
    <div @click="append('5')" class="btn">5</div>
    <div @click="append('6')" class="btn">6</div>
    <div @click="subtraction" class="btn operator">-</div>
    <div @click="append('1')" class="btn">1</div>
    <div @click="append('2')" class="btn">2</div>
    <div @click="append('3')" class="btn">3</div>
    <div @click="addition" class="btn operator">+</div>
    <div @click="append('0')" class="btn zero">0</div>
    <div @click="dot" class="btn operator">.</div>
    <div @click="equal" class="btn operator">=</div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      previous: null,
      current: "",
      operator: null,
      operatorClicked: false
    };
  },
  methods: {
    clear() {
      this.current = "";
    },
    append(number) {
      if (this.operatorClicked) {
        this.current = "";
        this.operatorClicked = false;
      }
      this.current += number;
    },
    sign() {
      if (this.current.length == "0" ) {
        this.current = "0";
      } else
        this.current =
          this.current.charAt(0) === "-"
            ? this.current.slice(1)
            : "-" + this.current;
    },
    perc() {
      this.current = parseFloat(this.current / 100) + "";
    },
    dot() {
      if (this.current.indexOf(".") === -1) {
        this.append(".");
      }
    },
    setPrevious() {
      this.previous = this.current;
      // this.current = '';
      this.operatorClicked = true;
    },
    multiplication() {
      this.setPrevious();
      this.operator = (a, b) => a * b;
    },
    division() {
      this.operator = (a, b) => a / b;
      this.setPrevious();
    },
    addition() {
      this.operator = (a, b) => a + b;
      this.setPrevious();
    },
    subtraction() {
      this.operator = (a, b) => a - b;
      this.setPrevious();
    },
    equal() {
      this.current = this.operator(
        parseFloat(this.previous),
        parseFloat(this.current)
      );
      this.previous = null;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.calculator {
  font-family: "Roboto Mono", monospace;
  width: 700px;
  margin: 100px auto;
  font-size: 36px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(50px, auto);
  background-color: rgb(226, 223, 223);
}
.calculator div {
  border: 3px solid #dcd0c0;
  padding-top: 20px;
  padding-bottom: 20px;
}
.disp {
  grid-column: 1/5;
  color: white;
  background-color: #373737;
}
.zero {
  grid-column: 1/3;
}
.btn {
  background-color: rgb(128, 121, 111);
  color: white;
}
.btn:hover {
  background-color: rgb(105, 102, 98);
  transition: 0.5s;
}
.operator {
  background-color: rgb(151, 122, 85);
}
.operator:hover {
  background-color: rgb(126, 98, 58);
  transition: 0.5s;
}
</style>
