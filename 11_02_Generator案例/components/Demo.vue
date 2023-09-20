<template>
  <h3>生成器函数实例</h3>
</template>

<script setup>
  // 异步编程
/*   function * timer(arg){
    setTimeout(()=>{ 
      console.log(arg);
      iterator.next(222)
    },1000) ; 

    let two = yield
    setTimeout(()=>{
      console.log(two);
      iterator.next(333)
    },2000);

    let three = yield
    setTimeout(()=>{
      console.log(three);
    },3000);
  }

  let iterator = timer('111') 
  // 触发generator的第一个代码段
  iterator.next() */


  // 第二种写法
  // function one(){
  //   setTimeout(()=>{
  //     console.log(111);
  //     iterator.next('AAA')
  //   },1000)
  // }

  // function two(){
  //   setTimeout(()=>{
  //     console.log(222);
  //     iterator.next('BBB')
  //   },2000)
  // }
  
  // function * timer2(){
  //   let a = yield one()
  //   console.log(a);
  //   let b = yield two()
  //   console.log(a, b);
  // }

  // let iterator = timer2()
  // iterator.next()

  function* gen() {
    let result = yield 3 + 5
    console.log(result)
    yield result
  }
 
  let it = gen()
  console.log(it.next())      // {value: 8, done: false}
  console.log(it.next())      // undefined    {value: undefined, done: false}
  console.log(it.next())      // {value: undefined, done: true}

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
