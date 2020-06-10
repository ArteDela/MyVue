<template>
	<div class="todo">
		<ul class="todo__list">
			<TodoItem v-for="todo in todos" :todo = "todo"/>
		</ul>
		<ul class="todo__list">
			<tomorrow v-for="todoTomorrow in todosTomorrow" :todoTomorrow = "todoTomorrow"/>
		</ul>
	</div>
</template>
<script>
	import TodoItem from'@/components/TodoItem'
	import tomorrow from'@/components/tomorrow'
	export default{
		props:['todos','todosTomorrow'],
		components:{
			TodoItem,tomorrow
		}
	}
</script>
<style>
	ul
	{
		list-style: none;
		padding: 0;
		margin: 0;
	}
</style>