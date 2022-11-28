<template>
	<h1>一个人的信息</h1>
	<h2>姓名: {{name}}</h2>
	<h2>年龄: {{age}}</h2>
	<h2>性别: {{sex}}</h2>
	<button @click="sayMe">说话vue2</button>
	<button @click="sayHello">说话vue3</button>
	<button @click="showData">展示数据vue2</button>
	<button @click="showData2">展示数据vue3</button>
</template>

<script>
import {h} from 'vue'
export default {
  name: 'App',
  components: {
    
  },
  data(){
	  return{
		  sex: '男'
	  }
  },
  methods:{
	  sayHello(){
		  alert(`听我说谢谢你,${this.name},${this.sex}`)
	  },
	  showData(){
		  console.log(this.name)
		  console.log(this.age)
		  console.log(this.sex)
		  this.sayMe()
		  this.sayHello()
	  }
  },
  
  //setup的数据方法等的表现形式
  setup(){
	  //数据
	  let name = "张三"
	  let age = 18
	  
	  //方法
	  function sayMe(){
		  alert(`我叫${name},今年${age}岁了。`)
	  }
	  
	  function showData2(){
		  console.log(name)
		  console.log(age)
		  sayMe()
		  //vue2的配置,在vue3中不可用.但vue3的数据可在vue2中被使用
		  // console.log(this.sex)
		  // this.sayHello()
	  }
	  
	  //返回一个对象(常用)
	  return {
		  name,
		  age,
		  sayMe,
		  showData2
	  }
	  
	  //返回一个函数(渲染函数) 首先要先导入h, h1是渲染格式(h2,h3等) 后面的是被渲染的内容
	  // return ()=>{ return h('h1','赵天雨')}
  }
}
</script>

<style>
/* #app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
} */
</style>
