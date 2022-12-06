<template>
    <div class="post">
        <div>
            <div>Номер поста: {{ post.id }}</div>
            <div><strong>Название: </strong>{{ post.title }}</div>
            <div><strong>Описаниие: </strong>{{ post.body }}</div>
        </div>
        
        <div class="post_btn">
            <my-button @click="$emit('remove', post)">Удалить</my-button>
        </div>
    </div>
</template>

<script>
    export default {
        props: {
            post: {
                type: Object,
                required: true,
            }
        }
    }
</script>

<style>
    .post {
        padding: 15px;
        border: 3px solid teal; 
        margin-top: 15px;
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
</style>