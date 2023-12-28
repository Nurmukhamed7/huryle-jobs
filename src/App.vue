<script setup lang="ts">
import { reactive, toRefs, ref } from 'vue'
import Job from './types/Job'

const jobs = ref<Job[]>([
	{ title: 123, location: 'ranch', salary: 44654, id: '1' },
	{ title: 'quarryman', location: 'mounatain', salary: 12313, id: '2' },
	{ title: 'flute player', location: 'wood', salary: 34535, id: '3' },
	{ title: 'fisherman', location: 'lake', salary: 75456, id: '4' },
	{ title: 'guard', location: 'valley', salary: 23452, id: '5' },
])

console.log(typeof jobs.value[0]?.title)
</script>

<template>
	<div class="app">{{ jobs[0].location }}</div>
</template>

<style scoped></style>
