<template>
  <h3>const 定义常量</h3>
</template>

<script setup>
  import {ref,onMounted,toRaw} from 'vue'

  // 声明常量
  const name = 'xhy'

  // 1.一定要赋初始值
  // const a;

  // 2.一般常量使用大写

  // 3.常量的值不能修改
  // name = 'liubo'

  // 4.块级作用域
  // {
  //   const a = 29
  // }
  // console.log(a);

  // 5.对于数组和对象的元素修改，不算作对常量的修改，不会报错
  // const person = {name:'xhy',age:29}
  // person.name = 'liubo'
  // console.log(person);

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
