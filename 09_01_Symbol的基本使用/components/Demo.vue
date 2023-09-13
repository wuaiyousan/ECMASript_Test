<template>
  <h3>Symbol的基本使用</h3>
</template>

<script setup>
  import {ref,onMounted} from 'vue'
  // 定义Symbol,函数创建
  // let s = Symbol();
  // console.log(s, typeof s);

  // let s2 = Symbol('xhy')
  // let s3 = Symbol('xhy')

  // console.log(s2, s3, s2===s3);

  // // 使用Symbol.for 创建Symbol类型数据
  // let s4 = Symbol.for('xhy2')
  // let s5 = Symbol.for('xhy2')

  // console.log(s4, typeof s4, s4 === s5);

  // 特点
  // 1.不能与其他数据进行运算
  // let s6 = Symbol('xhy') + 20
  // let s6 = Symbol('xhy') > 20
  // let s6 = Symbol('xhy') + '222'

  // Symbol 创建对象属性

  // 向对象中添加方法 
  let game = {
    name: '俄罗斯方块',
    up: function(){
      console.log('普通方法up');
    },
    down: function(){
      console.log('普通方法down');
    }
  }
  // console.log(game);
  // game.up()

  // 给对象添加由symbol定义的方法属性。 第一种方法
  let fnList = {
    up: Symbol('up'),
    down: Symbol('down')
  }
  game[fnList.up] = function(){
    console.log('Symbol定义的up函数');
  }
  game[fnList.down] = function(){
    console.log('Symbol定义的down函数');
  }
  //console.log(game);
  game.up()

  //console.log(Reflect.ownKeys(game));

  let fnArr = Reflect.ownKeys(game)
  fnArr.forEach(it=>console.log(it))

  // game[Reflect.ownKeys(game)[4]]()

  // 给对象添加由symbol定义的方法属性。 第二种方法
  let car = {
    name: 'lsls',
    [Symbol('price')]: function() {
      console.log('我是Symbol定义的方法');
    },
  }
  // 调用对象中symbol创建的方法
  car[Reflect.ownKeys(car)[1]]()
  car[up]()
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
