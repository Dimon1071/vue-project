<template>
    <div>
      <h3>Список постов:</h3>
      <transition-group name="user-list">
        <post-item 
          :post="post" v-for="post in posts" 
          :key="post.id" 
          @remove="$emit('remove', post)" />
      </transition-group>
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
  .user-list-item {
    display: inline-block;
    margin-right: 10px;
  }

  .user-list-enter-active,
  .user-list-leave-active {
    transition: all 0.4s ease;
  }
  
  .user-list-enter-form,
  .user-list-leave-to {
    opacity: 0;
    transform: translateX(130px);
  }

  .user-list-move {
    transition: transform 0.8s ease;
  }
</style>