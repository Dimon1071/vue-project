<template>
    <div>
      <h3>Список постов:</h3>
        <post-item 
          :post="post" v-for="post in posts" 
          :key="post.id" 
          @remove="$emit('remove', post)" />
    </div>
        
</template>

<script>
 import PostItem from "./PostItem.vue";
 export default {
    components: {PostItem},
    props: {
       posts: {
         type: Array,
         required: true,
       }
    }
 }
</script>

<style>

    
</style>