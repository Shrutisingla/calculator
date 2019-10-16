<template>
  <div class="calculator-container">
    <h3>Calculator</h3>
    <div>
      <span @click="select(1)" class="my-btn col-xs-4">1</span>
      <span @click="select(2)" class="my-btn">2</span>
      <span @click="select(3)" class="my-btn">3</span>
      <span @click="select('x')" class="my-btn opr">*</span>
    </div>
    <div>
      <span @click="select(4)" class="my-btn">4</span>
      <span @click="select(5)" class="my-btn">5</span>
      <span @click="select(6)" class="my-btn">6</span>
      <span @click="select('+')" class="my-btn opr">+</span>
    </div>
    <div>
      <span @click="select(7)" class="my-btn">7</span>
      <span @click="select(8)" class="my-btn">8</span>
      <span @click="select(9)" class="my-btn">9</span>
      <span @click="select('/')" class="my-btn opr">/</span>
    </div>
    <div>
      <span @click="cal()" class="my-btn opr">=</span>
      <span @click="select(0)" class="my-btn">0</span>
      <span @click="select('-')" class="my-btn opr">-</span>
      <span @click="clear()" class="my-btn opr">C</span>
    </div>
    <input type="text" oninput="this.value = this.value.replace(/[^0-9.]/g, '').replace(/(\..*)\./g, '$1');" v-model="number"></input>
  </div>

</template>
<script>
import axios from 'axios';
export default {
    data() {
        return {
          number:''
        }
    },
    methods: {
      select(input){
        this.number += input
      },
      cal(){
        let total = this.number
        return this.number = eval(total)
      },
      clear(){
        this.number=''
      }
    }
  }

</script>
<style scoped>
.my-btn{
  display: inline-block;
  border: 1px solid #dedddd;
  background: white;
  margin: 2px 0;
  cursor: pointer;
  width: 45px;
  height: 20px;
  text-align: center;
  padding: 20px;
  font-size:20px;
}
.my-btn:hover{
  background:#dedddd;
  box-shadow:0px 3px 10px rgba(0, 0, 0, 0.3);
}
.my-btn.opr{
  background:#f1f1f1;
}
.my-btn.opr:hover{
  background: #0000ff;
  color:white;
}
input{
  height: 20px;
  padding: 20px;
  width: 320px;
  margin: 2px 0;
  background: #dedddd;
  border: none;
  font-size: 20px;
  font-weight: 700;
  letter-spacing: 5px;
}
.calculator-container{
  text-align:center;
}
</style>
