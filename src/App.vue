<template>
	<div id="app">
		<p>На сегодня <span>{{tomorrowDay + " " + monthsArr[tomorrowDate] + ' ' + tomorrowYear + ' г'}}</span></p>
		<TodoList :todos = "todos"/>
		<p>На завтра <span>{{tomorrowDay + 1 + " " + monthsArr[tomorrowDate] + ' ' + tomorrowYear + ' г'}}</span></p>
		<TodoList :todosTomorrow = "todosTomorrow"/>
		<TodoButton @newItem = "newItem"/>
	</div>
</template>

<script>
	import TodoList from'@/components/TodoList'
	import TodoButton from'@/components/TodoButton'
	export default {
		name: 'App',
		data(){
			return{
				monthsArr: ["Января", "Февраля", "Марта", "Апреля", "Мая", "Июня",
				"Июля", "Августа", "Сентября", "Октября", "Ноября", "Декабря"],
				todos:[
					{
						id:1,
						title:'Выспаться',
						isActive:false
					},
					{
						id:2,
						title:'ЧТо то еще замутить',
						isActive:false
					},
					{
						id:3,
						title:'Пожать 200кг',
						isActive:false
					},
					{
						id:4,
						title:'Убить Билла',
						isActive:false
					},
				],
				todosTomorrow:[
					{
						id:'',
						title:'Купить хлеб',
						isActive:false
					},
					{
						id:'',
						title:'Купить сыр',
						isActive:false
					},
					{
						id:'',
						title:'Купить молоко',
						isActive:false
					}
				],
				nextID: 5,
				tomorrowDate: new Date().getMonth(),
				tomorrowDay: new Date().getDate(),
				tomorrowYear: new Date().getFullYear(),
			}
		},
		created(){
		},
		methods:{
			newItem(){
				this.todos.push({
					id:this.nextID++,
					title:'Новая задача',
					isActive:false
				})
			},
			myDate(){

			}
		},
		components: {
			TodoList,//указываю таким образом потому что ключ и значение совпадают
			TodoButton,
		}
	}
</script>

<style>
@font-face {
	font-family: 'Roboto';
	src: url('~@/fonts/Roboto/Regular/Roboto-Regular.eot');
	src: url('~@/fonts/Roboto/Regular/Roboto-Regular.eot?#iefix') format('embedded-opentype'),
		url('~@/fonts/Roboto/Regular/Roboto-Regular.woff2') format('woff2'),
		url('~@/fonts/Roboto/Regular/Roboto-Regular.woff') format('woff'),
		url('~@/fonts/Roboto/Regular/Roboto-Regular.ttf') format('truetype');
	font-weight: normal;
	font-style: normal;
}
@font-face {
	font-family: 'Roboto';
	src: url('~@/fonts/Roboto/Bold/Roboto-Bold.eot');
	src: url('~@/fonts/Roboto/Bold/Roboto-Bold.eot?#iefix') format('embedded-opentype'),
		url('~@/fonts/Roboto/Bold/Roboto-Bold.woff2') format('woff2'),
		url('~@/fonts/Roboto/Bold/Roboto-Bold.woff') format('woff'),
		url('~@/fonts/Roboto/Bold/Roboto-Bold.ttf') format('truetype');
	font-weight: bold;
	font-style: normal;
}

body
{
	background: #E5E5E5;
}
#app {
	font-family: 'Roboto';
	margin: auto;
	text-align: center;
	padding: 20px;
	color: #2c3e50;
	margin-top: 60px;
	width: 473px;
	border-radius: 4px;
	background:white;
}
span
{
    font-family: 'Roboto';
	font-weight: bold;
}
label{font-size: 14px}
p
{
	text-align: left;
	margin-bottom: 7px;
	font-size: 14px;
}
</style>
