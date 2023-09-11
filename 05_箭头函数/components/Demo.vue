<template>
  <h3>箭头函数</h3>
</template>

<script setup>
  import { reactive } from "vue";

  // ES6 允许箭头定义函数 
  // 声明函数
  let fn = (a, b)=>{
    return a+b
  }
 
  // 调用函数
  let result = fn(1, 2)
  console.log(result);

  // 1.this是静态的，this始终指向函数声明时所在作用域下的this的值
  // 2.不能作为构造函数实例化对象
  // 3.内部不能使用 arguments 属性，arguments属性：函数内部用于保存实参
  // 4.箭头函数的简写方式
  // 4.1 简写小括号：当形参有且只有一个的时候
  // 4.2 简写大括号：当函数体只有一条语句的时候，此时return关键字也必须省略


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
