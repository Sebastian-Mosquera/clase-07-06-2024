<script setup>
import {ref } from 'vue'

const users = ref([])
function loadData() {
	fetch('https://jsonplaceholder.typicode.com/users')
	.then(function(response){
		return response.json()
	})
	.then(function(data) {
		console.log(data)
		users.value = data
	})


}
</script>

<template>
	<div
	v-for="user in users"
	:key="users.id"
	class="bg-slate-300 mb-1 mt-4 text-center rounded-x1 p-2 max-w-60 mx-auto"
	>
	{{ user.name }}
	</div>
	<button @click="loadData" class="rounded-x1 border bg-green-400 flex p-2 max-w-60 mx-auto mt-12">
		cargar info
	</button>
</template>