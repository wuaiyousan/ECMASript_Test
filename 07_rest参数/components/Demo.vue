<template>
  <h3>rest参数</h3>
</template>

<script setup>
  // ES6 提供了rest参数，用于获取函数的实参，用来替代arguments

  // ES5获取实参
  function person(){
    console.log(arguments);
  }
  person('xhy','lb','ck') // 输出为对象

  // ES6 rest参数获取实参
  function car(...other){
    console.log(other);
  }
  car('byd','bc') // 输出为函数

  // rest参数必须要放到参数的最后
  // function rooms(a, b, c, ...other){
  //   console.log(a, b, c, other);
  // }
  // rooms('101', '102', '103', 104, 105, 106)

  // 
  let school = (...args)=>console.log(args);
  
  school('jsdx','zndx')

</script>

<style>
  .list{
    display: flex;
    flex-direction: row;
  }
  .item{
    width: 60px;
    height: 30px;
    border: 1px solid #000;
    margin-left: 10px;
  }
</style>
