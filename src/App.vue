<template>
    <div class="app">
        <post-form
        @create="createPost"/>
        <post-list :posts-prop="posts"/>
    </div>
</template>

<script>
    import PostForm from "@/components/PostForm";
    import PostList from "@/components/PostList";
    export default {
        components: {
            PostList, PostForm
        },
        data(){
            return{
                posts: [
                    {id: 1, title: 'Title 1', body: 'OEgnousdlvuohrs'}, //объекты
                ],
            }
        },
        methods:{
            createPost(post){
                this.posts.push(post);
            }
        }
    }
</script>

<style>
*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
}
    .app{
        padding: 15px;
    }
</style>

