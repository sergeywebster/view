<template>
	<div class="app">
		<div>
			<button @click="addLike">Like</button>
			<button @click="addDislike">Dislike</button>
		</div>
		<div>Количество лайков: <strong>{{ likes }}</strong></div>
		<div>Количество дизлайков: <strong>{{ dislikes }}</strong></div>
		<post-form  @create="createPost"/>
		<post-list  v-bind:posts="posts" />
	</div>
</template>

<script>

import PostList from "./components/PostList";
import PostForm from "@/components/PostForm";

export default {
	components: {
		PostList, PostForm
	},

	data() {
		return {
			likes: 0,
			dislikes: 0,
			posts: [
				{id: 1, title: 'Javascript', text: 'Содержание статьи'},
				{id: 2, title: 'Javascript 2', text: 'Содержание статьи 2'},
				{id: 3, title: 'Javascript 3', text: 'Содержание статьи 4'}
			],
		}
	},
	methods: {
		addLike() {
			this.likes += 1;
		},

		addDislike() {
			this.dislikes -= 1;
		},

		createPost(post) {
			this.posts.push(post);
		},
	}
}

</script>

<style>
* {
	margin: 0px;
	padding: 0px;
	box-sizing: border-box;
}

.app {
	max-width: 860px;
	margin: 0px auto;
	padding: 20px;
}

</style>

