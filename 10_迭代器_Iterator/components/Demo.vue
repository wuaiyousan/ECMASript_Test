<template>
  <h3>迭代器</h3>
</template>

<script setup>
  // 声明一个数组
  const car = ['lsls','bc','bm']

  // 使用for...of 循环
  // for(let i of car){
  //   console.log('for...of',i);
  // }

  //console.log(car);

  // 工作原理
  let iterator = car[Symbol.iterator]()
  //console.log(iterator);

  // console.log(iterator.next()); 
  // console.log(iterator.next()); 
  // console.log(iterator.next()); 
  // console.log(iterator.next()); 


  // 自定义遍历数据
  let person = {
    name: 'xhy',
    hobby: ['打游戏','写代码','看视频'],
    [Symbol.iterator](){
      let index = 0;
      let self = this
      return {
        next(){
          if(index < self.hobby.length){
            const result =  {value: self.hobby[index], done: false}
            index ++
            return result
          }else{
            return {value: undefined,done: true}
          }
        }
      }
    }
  }

  for(let i of person){
    console.log(i);
  }
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
