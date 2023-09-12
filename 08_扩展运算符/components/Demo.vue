<template>
  <h3>扩展运算符</h3>
  <div ref="list">
    <div class="item"></div>
    <div class="item"></div>
    <div class="item"></div>
  </div>
</template>

<script setup>
  import {ref,onMounted} from 'vue'

  // ES6 【...】 扩展运算符能将数组转化为逗号分隔的 参数序列
  function rooms(){
    console.log(arguments);
  }
  const roomList = [101, 102, 103]
  rooms(...roomList) // rooms(101, 102, 103)

  // 扩展运算符的应用
  // 1.数组的合并
  const english = [20, 60, 75]
  const chinese = [80, 54]

  const tatol = english.concat(chinese) // ES5 数组的concat方法
  const tatolES6 = [...english,...chinese]

  console.log(tatol,'---',tatolES6);

  // 2.数组的克隆
  const car = ['bc','lsls','byd']
  const newCar = [...car]

  console.log(newCar);

  // 3.将伪数组转化为真正的数组
  const list = ref()
  onMounted(() => { 
    const children = list.value.children;

    const divChildren = [...children]
    console.log(divChildren);
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
