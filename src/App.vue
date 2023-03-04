<template>
  <div id="app">
    <h1>helllo</h1>
    <div class="posts">
      <div class="post"><input  
      type="text"  
      placeholder="post name"
      v-model="title">
      <!-- V-MODELLL -->
      </div>
      <div class="post">
        <input 
        type="text"  
        placeholder="post text"
        v-model="text" 
        >
        <!-- двойное связывание vyshe -->
      </div>
      <button class="post" @click="addPost">Post</button>
    </div>
    <h2>Post list</h2>
    <div
    v-if="posts.length ===0">Tut nicho net</div>
    <div  v-for="(post,id) in posts"
    :key="id" 
    class="new" 
    >
      <div><button 
        @click="deletePost(id)"
        >
        delete
      </button></div>
      <h4>Title: {{ post.title }}</h4>
      <p><strong>Text:</strong>{{ post.text }}</p>
  
    </div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
      posts : [
        {
          id:1,
          title:'r',
          text:'e',
        },
        {
          id:2,
          title:'4',
          text:'dsf'
        }
      ],
      title: '',
      text: '',
    }
  },
  methods:{
    addPost(){
      this.posts.push({
        title:this.title,
        text:this.text,
      })
      this.title = this.text = ''
    },
    deletePost(id){
      this.posts.splice(id,1)
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 40px;
}
.posts{
  display:flex;
  flex-direction:column;
  justify-content:center;
}
.post{
  margin-top:20px;
  display:flex;
  justify-content:center;

}
input{
  width:70%;
  height:30px;
}
button{
  width:70px;
  height:40px;
  text-align:center;
  margin-left: 48%;
}
.new{
  display:flex;
  flex-direction:column;
  border: 3px solid black;
  background-color: rgb(187, 185, 185);
  font-size:16;
  margin-bottom:5px;
}
</style>
