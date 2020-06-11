<template>
	<li class="todo__list-item" :class="{active:todoTomorrow.isActive}">
		<label class="g-checkbox todo__list-check">
			<input type="checkbox" class="g-checkbox__input" @change = "decorItemTomorrow(todoTomorrow)">
			<div class="g-checkbox__body">
				<span class="g-checkbox__box"></span>
			</div>
		</label>
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