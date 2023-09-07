<template>
  <h3>DEMO</h3>
</template>

<script setup>
  // 声明变量
  let a;
  let q,t,j;

  let c = 100;
  let b = [2,5], g = 'xhy'; 

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
  {
    let name = 'xhy';
    function fn(){
      console.log(name);
    }
    fn()
  }

</script>
