<template>
    <div>
        <form @submit.prevent>
            <h3>Создайте пост</h3>
            <input
                    v-model="post.title"
                    class="input"
                    type="text"
                    placeholder="Название">
            <input
                    v-model="post.body"
                    class="input"
                    type="text"
                    placeholder="Содержимое">
            <button class="btn" @click="createPost">Создать</button>
        </form>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                post: {
                    title: '',
                    body: ''
                }
            }
        },
        methods: {
            createPost(){
                this.post.id = Date.now();
                this.$emit('create', this.post);
                this.post = {
                    title: '',
                    body: ''
                }
            }

        }
    }
</script>

<style scoped>
    form{
        display: flex;
        flex-direction: column;
        max-width: 500px;
        gap: 10px;
    }
    .btn{
        align-self: flex-end;
        border: 1px solid olivedrab;
        color: olivedrab;
        background: none;
        padding: 10px;
    }
    .input{
        border: 2px solid olivedrab;
        padding: 10px;
    }
</style>