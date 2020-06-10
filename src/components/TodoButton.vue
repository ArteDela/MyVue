<template>
	<button class="button" @click = "$emit('newItem')">Добавить задачу</button>
</template>
<style>
	.button
	{
		padding: 15px;
		width: 473px;
		color:white;
		background: #27AE60;
		border-radius: 4px;
		border:none;
		outline: none;
		font-size: 16px;
	}
</style>