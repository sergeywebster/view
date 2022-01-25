<template>
	<div class="post" v-for="post in posts">
		<div><strong>Название: </strong>{{ post.title }}</div>
		<div><strong>Описание: </strong>{{ post.text }}</div>
	</div>
</template>

<script>
export default {
	props: {
		posts: {
			type: Array,
			required: true
		}
	}
}
</script>

<style scoped>
	.post {
		padding: 8px;
		margin: 15px 0px;
		border: 2px solid teal;
	}
</style>


