<template>
	<form @submit.prevent action="">
		<h3>Создание поста</h3>
		<my-input v-model="post.title"  type="text" placeholder="Название"/>
		<my-input v-model="post.body"  type="text" placeholder="Описание"/>
		<my-button 
		style="align-self: flex-end" 
		@click="createPost"
		>
		Создать
		</my-button>
	</form>
</template>

<script>

export default {
    data() {
        return {
            post: {
                title: "",
                body: ""
            }
        };
    },
    methods: {
        createPost() {
            this.post.id = Date.now();
            this.$emit("create", this.post);
            this.post = {
                title: "",
                body: ""
            };
        }
    },
}
</script>

<style>


form {
	display: flex;
	flex-direction: column;
}

</style>
