<template>
  <h3>生成器</h3>
</template>

<script setup>
  // 生成器其实就是一个特殊的函数
  // 生成器 generator 的初体验
  //#region 
/*   function * gen(a,b,c){
    // yield 可视为函数代码的分隔符
    // console.log('xhy001',a,b,c);
    yield {value:'第一部分代码结束',done: false}

    // console.log('xhy002',a,b,c);
    yield {value:'第二部分代码结束',done: true}

    // console.log('xhy003');
    yield {value:'第三部分代码结束',done: false}

    // console.log('xhy004');
  }

  let iterator = gen(1,2,3)
  // console.log(iterator);

  // 执行 generator
  console.log(iterator.next()); 
  console.log(iterator.next()); 
  console.log(iterator.next()); 
  console.log(iterator.next()); 

  // for...of 遍历
  // for(let i of iterator){
  //   if(i.done){
  //     console.log('遍历的回调',i);
  //   }
  // } */
  //#endregion

  // 生成器的参数传递
  function * gen(arg){
    console.log('arg', arg);
    let one = yield [111,arg]

    console.log('one', one);
    let two = yield [222, one, arg]

    console.log('two', two);
    let three = yield [333,two]
    
    console.log('three', three)
  }

  let iterator = gen('AAA')
  // 第一次的next() 不需要传递参数，第一部分可以使用生成器本身接收的参数
  console.log('这是第一段代码段的返回结果:',iterator.next())
  // 本次通过next() 传递参数，将作为上一次yield语句的返回结果，然后可以被本次代码块使用 
  console.log('这是第二段代码段的返回结果:',iterator.next('BBB'))

  console.log('这是第三段代码段的返回结果:',iterator.next('CCC'))
  console.log('这是第四段代码段的返回结果:',iterator.next('DDD'))

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
