<template>
	<li class="todo__list-item" :class="{active:todo.isActive}">
		<label class="g-checkbox todo__list-check">
			<input type="checkbox" class="g-checkbox__input" @change = "decorItem(todo)">
			<div class="g-checkbox__body">
				<span class="g-checkbox__box"></span>
			</div>
		</label>
		<label class="todo__list-text" contenteditable="true">{{todo.title}}</label>
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
	.g-checkbox
	{
		position: relative;
		font-size: 0;
		display: block;
	}
	.g-checkbox__input
	{
		position: absolute;
		width: 0;
		height: 0;
		top: 0;
		left: 0;
		z-index: -10;
		visibility: hidden;
		opacity: 0;
	}
	.g-checkbox__input:enabled~ .g-checkbox__body
	{
		display:flex;
		align-items: center;
		cursor: pointer;
	}
	.g-checkbox__input:enabled:checked ~ .g-checkbox__body .g-checkbox__box
	{
		background: #6FCF97;
		background-image: url('~@/assets/svg/check.svg');
		background-repeat: no-repeat;
		background-position: center center;
	}
	.g-checkbox__box
	{
		width: 22px;
		height: 22px;
		background: #F2F2F2;
		border: 1px solid #E0E0E0;
		border-radius: 3px;
		display: inline-block;
		vertical-align: top;
	}


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