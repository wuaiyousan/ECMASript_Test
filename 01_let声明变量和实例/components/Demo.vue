<template>
  <h3>DEMO</h3>
  <h4>点击变换颜色</h4>
  <div class="list" ref="list">
    <div class="item" ref="item"></div>
    <div class="item" ref="item"></div>
    <div class="item" ref="item"></div>
  </div>

</template>

<script setup>
  import {ref,onMounted,toRaw} from 'vue'
  //#region 
  // ---声明特性---
  // 1.不能重复声明对象  ---var 可以声明重复变量
  // let name = 'xhy';
  // let name = 'liubo';

  // 2.块级作用域  全局，函数，eval。三种作用域
  // if,else,whil,for
  // {
  //   let name = 'xhy'
  // }
  // console.log(name);

  // 3.不存在变量提示
  // console.log(name);
  // let name = 'xhy'

  // 4.不影响作用域链
  // {
  //   let name = 'xhy';
  //   function fn(){
  //     console.log(name);
  //   }
  //   fn()
  // }
  //#endregion

  // ---案例---
  // 获取DOM元素
  const item = ref()
  const list = ref()

  onMounted(() => {
    // console.log('xhy001',item.value);

    // console.log('xhy002',list.value.childNodes);

    // console.log('xhy003',list.value.childNodes[0].style.backgroundColor);

    // 遍历并绑定事件
    // list.value.childNodes.forEach((i) => {
    //   i.onclick = function(){
    //     // 修改当前元素的背景颜色
    //     i.style.backgroundColor = '#000000'
    //   }
    // });

    let items = list.value.childNodes
    // for(var i = 0; i < items.length; i++){
    //   items[i].onclick = function(){
    //     items[i].style.backgroundColor = '#000000'
    //   }
    // }

    for(let i = 0; i < items.length; i++){
      items[i].onclick = function(){
        items[i].style.backgroundColor = '#000000'
      }
    }

    // 当用let定义时形似如下代码，执行点击事件的回调时，向外寻找let i = 0。不会再去外层找变量i
    // {
    //   let i = 0 
    //   items[i].onclick = function(){
    //     items[i].style.backgroundColor = '#000000'
    //   }
    // }
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
