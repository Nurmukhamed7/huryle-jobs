<template>
	<div class="app">
		<button @click="handleClick('title')">order by title</button>
		<button @click="handleClick('salary')">order by salary</button>
		<button @click="handleClick('location')">order by location</button>

		<JobList :jobs="jobs" :order="order" />
	</div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import Job from './types/Job'
import OrderTerm from './types/OrderTerm'

import JobList from './components/JobList.vue'

const jobs = ref<Job[]>([
	{ title: 'farmer', location: 'ranch', salary: 44654, id: '1' },
	{ title: 'quarryman', location: 'mounatain', salary: 12313, id: '2' },
	{ title: 'flute player', location: 'wood', salary: 34535, id: '3' },
	{ title: 'fisherman', location: 'lake', salary: 75456, id: '4' },
	{ title: 'guard', location: 'valley', salary: 23452, id: '5' },
])

const order = ref<OrderTerm>('title')

const handleClick = (term: OrderTerm) => {
	order.value = term
}
</script>

<style scoped></style>
