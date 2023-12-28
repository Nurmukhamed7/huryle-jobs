<template>
	<div class="job-list">
		<p>Ordered by {{ order }}</p>
		<ul>
			<li class="card" v-for="job in orderedJobs" :key="job.id">
				<h2>{{ job.title }} in {{ job.location }}</h2>
				<div class="salary">
					<p>{{ job.salary }} dollars</p>
				</div>
				<div class="description">
					<p>
						Lorem ipsum dolor sit amet, consectetur adipisicing elit. Odit
						tenetur nihil saepe perspiciatis sint provident alias nulla, enim
						laudantium unde.
					</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script setup lang="ts">
import { PropType, computed, defineProps } from 'vue'
import Job from '../types/Job'
import OrderTerm from '../types/OrderTerm'

const props = defineProps({
	jobs: { type: Array as PropType<Job[]>, required: true },
	order: { type: String as PropType<OrderTerm>, required: true },
})

const orderedJobs = computed(() => {
	return [...props.jobs].sort((a: Job, b: Job) => {
		return a[props.order] > b[props.order] ? 1 : -1
	})
})
</script>

<style scoped>
.card {
	background: rgb(210, 200, 63);
}
</style>
