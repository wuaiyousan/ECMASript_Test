<template>
  <h3>Symbol的内置值</h3>
</template>

<script setup>
  // 用于监测数据类型
  class Person{
    static [Symbol.hasInstance](param){
      console.log(param,'我被用于类型监测了');
    }
  }
  let o = {}

  // console.log(o instanceof Person);

  // isConcatSpreadable 用于判断数组合并时是否是展开合并，
  // 优先级低于 [...arr1,...arr2]。扩展运算符本身就会将数组展开
  let arr1 = [1,2,3]
  let arr2 = [4,5,6]
  arr2[Symbol.isConcatSpreadable] = false
  // console.log([...arr1,...arr2]);
  // console.log(arr1.concat(arr2));

  // 对象的 Symbol.split 属性，指向一个方法，当该对象被 String.prototype.split 方法调用时，会返回该方法的返回值。
  // let str1 = 'x_h_y'

  // class Sp{
  //   [Symbol.split](param){  
  //     //console.log('xhy003',param.split('_'));
  //     return param.split('_');
  //   }
  // }

  // console.log(str1.split(new Sp())); 
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
