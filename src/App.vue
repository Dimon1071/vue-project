<template>
  <div class="app">
    <form @submit.prevent>
      <h4>Создание поста</h4>
      <input
       @input="title = $event.target.value" 
       :value="title" 
       class="input" 
       type="text" 
       placeholder="Название">

      <input
      @input="body = $event.target.value" 
      :value="body" 
      class="input" 
      type="text" 
      placeholder="Описание">

      <button @click="addPost">Создать</button>
    </form>

    <div class="post" v-for="post in posts">
      <div><strong>Название: </strong>{{ post.title }}</div>
      <div><strong>Описаниие: </strong>{{ post.body }}</div>
    </div>
  </div>
</template>

<script>

  export default {
    data(){
      return {
        posts: [
          {id: 1, title: 'JavaScript 1', body: 'описание поста'},
          {id: 2, title: 'JavaScript 2', body: 'описание поста 2'},
          {id: 3, title: 'JavaScript 3', body: 'описание поста 3'},
        ],
        title: '',
        body: '',
      }
    },
    methods: {
      addPost() {
        const newPost = {
          id: Date.now(),
          title: this.title,
          body: this.body,
        }
        this.posts.push(newPost);
        this.title = '';
        this.body = ''; 
      }
    }
  }
</script>

<style>

 * {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
 }

.post {
  padding: 15px;
  border: 3px solid teal; 
  margin-top: 15px;
}

.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}

.app {
  padding: 15px;
}

</style>




