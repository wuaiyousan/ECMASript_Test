<template>
  <h3>生成器函数实例_2</h3>
</template>

<script setup>
// var myIterable = {};
// myIterable[Symbol.iterator] = function* () {
//   yield 1;
//   yield 2;
//   yield 3;
// };

// [...myIterable] // [1, 2, 3]
// console.log([...myIterable]);

/***********************************************************/
// function* add(){
//   yield 1;
//   yield 2;
//   yield 3;
// }

// let o = add()
// console.log([...o]);

/***********************************************************/
// function* f() {
//   for(var i = 0; true; i++) {
//     var reset = yield i;
//     console.log(reset, i ,);
//     if(reset) { 
//       console.log('xhy001', i);
//       i = -1; 
//     }
//   }
// }

// let gen = f()
// console.log(gen.next()); 
// console.log(gen.next(0)); 
// console.log(gen.next()); 
// console.log(gen.next()); 
// console.log(gen.next()); 

/***********************************************************/
// function* foo(x) {
//   var y = 2 * (yield (x + 1));
//   var z = yield (y / 3);
//   return (x + y + z);
// }

// let o = foo(5)

// // o.next()  // {value: 6, done: false }
// // o.next()  // {value: NAN, done: false}
// // o.next()  // {value: NAN, done: true}

// // console.log(o.next());
// // console.log(o.next());
// // console.log(o.next());

// // o.next()  // {value: 6, done: false }
// // o.next(12)  // {value: 8, done: false}
// // o.next(13)  // {value: 42, done: true} 5+24+13

// console.log(o.next());
// console.log(o.next(12));
// console.log(o.next(13));

/***********************************************************/
// function* dataConsumer() {
//   console.log('Started');
//   console.log(`1. ${yield}`);
//   console.log(`2. ${yield}`);
//   return 'result';
// }
// let genObj = dataConsumer();

// // genObj.next() // {value: underfined, done: false }
// // genObj.next('a') // {value: underfined, done: false }
// // genObj.next('b') // {value: result, done: true }

// console.log(genObj.next());
// console.log(genObj.next('a'));
// console.log(genObj.next('b'));

/***********************************************************/
// function* foo(){
//   yield 1;
//   yield 2;
//   yield 3;
//   yield 4;
//   yield 5;
//   return 6
// }

// for(let o of foo()){
//   console.log(o);
// }

/***********************************************************/
// let person = {name: 'xhy', age: 18}
// // 使用for...of循环遍历对象的第一种方法
// // function* objectEntries(obj){
// //   let objKeys = Reflect.ownKeys(obj)

// //   for(let o of objKeys){
// //     yield [o, obj[o]]
// //   }
// // }

// // for(let [key, value] of objectEntries(person)){
// //   console.log(key,value);
// // }

// // 使用for...of循环遍历对象的第二种方法
// function* objectEntries(){
//   let objKeys = Reflect.ownKeys(this)
//   for(let o of objKeys){
//     yield [o,this[o]]
//   }
// }
// person[Symbol.iterator] = objectEntries
// for(let [key, value] of person){
//   console.log(key,value);
// }

/***********************************************************/
let g = function* () {
  try {
    yield 'xhy';
  }catch(e) {
    console.log('内部捕捉', e);
  }

  try {
    yield 'xhy2';
  }catch(e) {
    console.log('内部捕捉', e);
  }
}
let i = g();
//i.next()
console.log('第一次next',i.next());

// i.throw('a')
// i.throw('b')

console.log(i.throw('a'));
console.log(i.throw('b'));



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
