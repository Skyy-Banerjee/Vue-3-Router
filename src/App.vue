<script setup>
import { RouterView, RouterLink } from 'vue-router';
</script>

<template>
	<main>
		<div class="links">
			<RouterLink active-class="active" to="/">Home</RouterLink>
			<RouterLink active-class="active" to="/about">About</RouterLink>
		</div>
		<RouterView />
	</main>
</template>

<style scoped>
.links {
	padding: 20px;
}

.links a {
	margin: 0 5px;
}

.active {
	font-weight: bold;
	color: rgb(15, 126, 85);
}
</style>
