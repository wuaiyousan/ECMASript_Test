<template>
  <h3>函数参数默认值</h3>
  <h3>{{sum}}</h3>
</template>

<script setup>
  // ES6 允许给函数参数赋值初始值

  // 1.形参的初始值。 具有默认值的参数，一般位置要靠后
  function add(a, b, c=10){
    return a + b + c;
  }
  let sum = add(1, 2)

  // 2.可以与解构赋值一起使用
  function person({name, age=29}){
    console.log(name,age);
  }
  person({
    name: 'xhy',
  })
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
