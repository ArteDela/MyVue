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
				todos:[],
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
				nextID: 1,
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
		},
		components: {
			TodoList,//указываю таким образом потому что ключ и значение совпадают
			TodoButton,
		}
	}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	margin: auto;
	text-align: center;
	padding: 20px;
	color: #2c3e50;
	margin-top: 60px;
	width: 473px;
	border-radius: 4px;
	box-shadow:  0 0 10px black
}
span
{
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
