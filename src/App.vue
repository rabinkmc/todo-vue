<template>
	<div id="add">
		<h1>To-Do lists</h1>
		<ul>
			<li v-for="item in toDoItems" :key="item.id">
				<to-do-item :id="item.id" :label="item.label" :done="item.done"></to-do-item>
			</li>
		</ul>
	</div>
</template>

<script>
import ToDoItem from './components/ToDoItem.vue';
import uniqueId from 'lodash.uniqueid'

export default {
	name: 'App',
	components: {
		ToDoItem
	},
	data() {
		return {
			toDoItems: [
				{id: uniqueId('todo-'), label: 'django signals', done: false},
				{id: uniqueId('todo-'), label: 'authentication', done: true},
				{id: uniqueId('todo-'), label: 'vue js-components', done: true},
			]
		}
	}
}
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	text-align: center;
	color: #2c3e50;
	margin-top: 60px;
}
</style>
