<template>
  <h3>简化对象写法</h3>
  <button @click="copyChagen">按钮</button>
</template>

<script setup>
  import { reactive } from "vue";

  // ES6 允许在大括号里，直接写入变量和函数，作为对象的属性和方法。书写更加简洁
  let name = 'xhy'
  let change = function(){
    console.log('22222');
  }

  let person = reactive({
    name,
    age: 29,
    handler: change,
    improve(){
      console.log('33333');
    }
  })

  person.handler()

  function copyChagen(){
    console.log(person);
    person.improve()
  }

  // ---案例---

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
