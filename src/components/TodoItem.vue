<template>
	<li class="todo__list-item" :class="{active:todo.isActive}">
		<input type="checkBox" class="todo__list-check" @change = "decorItem(todo)">
		<label class="todo__list-text" contenteditable="true">{{todo.title}} {{todo.id}}</label>
	</li>
</template>
<script>
	export default{
		props:['todo'],
		methods:{
			decorItem(item){
				item.isActive = !item.isActive
			}
		}
	}
</script>
<style>
	.todo__list-item
	{
		display: flex;
		align-items: center;
		justify-content: left;
		margin-bottom: 23px;
	}
	.active
	{
		text-decoration: line-through;
		opacity: 0.7;
	}
	.todo__list-text
	{
		width:100%;
		text-align: left;
	}
	.todo__list-text:focus
	{
		border: none;
		outline: none;
	}
	.todo__list-check
	{
		width: 24px;
		height: 24px;
		margin: 0;
		margin-right: 12px;
	}
</style>