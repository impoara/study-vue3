<template>
	<h1>一个人的信息</h1>
	<h2>姓名: {{person.name}}</h2>
	<h2>年龄: {{person.age}}</h2>
	<h3>工作种类: {{person.job.type}}</h3>
	<h3>工作薪水: {{person.job.salary}}</h3>
	<h3>爱好: {{person.hobby}}</h3>
	<h3>测试数据: c: {{person.job.a.b.c}}</h3>
	<button @click="changeInfo">修改个人信息</button>
</template>

<script>
import {ref, reactive} from 'vue'
export default {
  name: 'App',
  components: {
    
  },
  //setup的数据方法等的表现形式
  setup(){
	  //数据
/* 	  let name = ref('张三')
	  let age = ref(18)
	  let job = reactive({
		  type:'前端工程师',
		  salary:'30k',
		  a:{
			  b:{
				  c:666
			  }
		  }
	  })
	  let hobby = reactive(['抽烟','喝酒','烫头']) */
	  let person  = reactive({
		  name: '张三',
		  age: 18,
		  job:{
			 type:'前端工程师',
			 salary:'30k',
			 a:{
			 	b:{
					c:666
				}
			 }
		  },
		  hobby: ['抽烟','喝酒','烫头']
	  })
	  
	  //方法
	  function changeInfo(){
		person.name = '李四'
		person.age = 48
		person.job.type = 'Java工程师'
		person.job.salary = '45k'
		person.job.a.b.c = 999
		person.hobby[0] = '学习'
		// console.log(name,age,job)
	  }
	  
	  //返回一个对象(常用)
	  return {
		 /* name,
		  age,
		  job,
		  hobby, */
		  person,
		  changeInfo,
	  }
	  
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
