<template>
	<form @submit.prevent>
		<h4>Create a post</h4>
		<input 
			v-model="post.title" 
			class="input" 
			type="text" 
			placeholder="Title">
		<input 
			v-model="post.text" 
			class="input" 
			type="text" 
			placeholder="Text">
		<button 
			class="btn" 
			@click="createPost"
			>Send
		</button>
	</form>
</template>

<script>
export default {
	data() {
		return {
			post: {
				title: '',
				text: ''
			}
		}
	},

	methods: {
		createPost() {
			this.post.id = Date.now()

			this.$emit('create', this.post)
			this.post = {
				title: '',
				text: ''
			}
		}
	}
}
</script>

<style scoped>
	form {
	display: flex;
	flex-direction: column;
}

form input {
	width: 100%;
	border: 1px solid teal;
	padding: 10px 15px;
	margin: 5px 0px;
}

form button.btn {
	align-self: flex-end;
	margin-top: 5px;
	background: teal;
	color: white;
	border: 0px;
	padding: 10px 15px;
	cursor: pointer;
}

</style>


