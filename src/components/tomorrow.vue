<template>
	<li class="todo__list-item" :class="{active:todoTomorrow.isActive}">
		<input type="checkBox" class="todo__list-check" @change = "decorItemTomorrow(todoTomorrow)">
		<label class="todo__list-text" contenteditable="true">{{todoTomorrow.title}}</label>
	</li>
</template>
<script>
	export default{
		props:['todoTomorrow'],
		methods:
		{
			decorItemTomorrow(item){
				item.isActive = !item.isActive
			}
		}
	}
</script>
<style>

</style>