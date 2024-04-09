<script setup>
import { useRoute, RouterView, useRouter } from 'vue-router';
import { ref, onBeforeMount } from 'vue';
import cars from '../data.json';

const car = ref(null);
const route = useRoute();
const router = useRouter();

const { id } = route.params;
onBeforeMount(() => {
	car.value = cars.find((c) => c.id === parseInt(id));
});
</script>

<template>
	<div class="container">
		<div v-if="car">
			<h1>The Car</h1>
			<p>Make: {{ car.make }}</p>
			<p>Body: {{ car.body }}</p>
			<p>Price: 💲{{ car.price }}</p>
			<p>Year: {{ car.year }}</p>
			<button @click="router.back()">Go Back ⬅️</button>
			<RouterView />
		</div>
		<div v-else>
			<h1>☹️ Oops!.. Car not foud ⚠️</h1>
		</div>
	</div>
</template>
