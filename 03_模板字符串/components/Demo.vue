<template>
  <h3>模板字符串</h3>
</template>

<script setup>
  // ES6引入新的声明字符串的方式  【 `` 】 
  // 声明
  // let str = `XHYWD`
  // console.log(str, typeof str);

  // 1.内容中可以直接出现换行符
  // let str = `<ul>
  //             <li>陈凯</li>
  //             <li>刘波</li>
  //             <li>光子</li>
  //           </ul>`
  // console.log(str);

  // 2.可以直接进行变量拼接
  let name = '熊海鹰'
  let str2 = `${name}，无敌啊！`
  console.log(str2);

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
