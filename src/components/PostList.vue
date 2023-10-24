<template>
    <div>
        <div v-for="post in postsProp" :key="post.id" class="post">
            <div>Название: {{ post.title }}</div>
            <div>Содержимое: {{ post.body }}</div>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            postsProp: {
                type: Array,
                required: true
            }
        }

    }
</script>

<style scoped>
.post{
    border: 2px solid olivedrab;
    width: 100%;
    padding: 15px;
    max-width: 500px;
    margin-top: 20px;
}
</style>