<template>
  <div class="home">
   <h1>Home</h1> 
   <PostList :posts="posts" v-if="showPosts"/>
   <button @click="showPosts = !showPosts">Toggle Posts</button>
   <button @click="posts.pop()">Delete Post</button>
   <!-- // ----------------------------------------------------------------// -->
   <!-- <input type="text" v-model="search"/>
   <p>Search term - {{ search }}</p>
   <div v-for="name in matchingNames" :key="name">
    {{ name }}
   </div>
   <button @click="handleClick">stop watching</button> -->
    <!-- // ----------------------------------------------------------------// -->
    <!-- <h2>Refs</h2> -->
    <!-- <p>My name is {{ name }} and my age is {{ age }}</p>
    <button @click="handleClick">click me</button>
    <button @click="age++">add 1 to age</button>
    <input type="text" v-model="name"/> -->

    <!-- // ----------------------------------------------------------------// -->
    <!-- <p>{{ userOne.name}} - {{ userOne.age}}</p>
    <button @click="updateUserOne">Update User One</button>
    <h2>Reactive</h2>
    <p>{{userTwo.name}} - {{ userTwo.age}} - {{ nameTwo }}</p>
    <button @click="updateUserTwo">Update User Two</button> -->
  </div>
</template>

<script>
import { ref, reactive } from '@vue/reactivity';
import { computed, watch, watchEffect } from '@vue/runtime-core';
import PostList from '../components/PostList.vue'


export default {
  name: 'HomeView',
  components: {PostList},
  setup(){
    const posts = ref([
      {title: 'Welcome to the blog', body: 'This is my blog, Lorem ipsum dolor sit, amet consectetur adipisicing elit. Exercitationem sequi nesciunt libero cum cupiditate nemo consequuntur nisi maiores at ipsa corrupti nobis, perferendis voluptate nulla amet saepe recusandae eaque incidunt?', id:1},
      {title: 'Top 5 CSS tips', body: 'Best tricks to implement CSS', id:2}
      
    ])

    const showPosts = ref(true)

    return {posts, showPosts}
    // ----------------------------------------------------------------//
    // const search = ref('')
    // const names = ref(['mario','yoshi','luigi','toad','bowser','koopa','peach'])

    // const stopWatch = watch(search, ()=>{
    //   console.log('watch function run')
    // })

    // const stopWatchEffect= watchEffect(()=>{
    //   console.log('watchEffect function run', search.value)
    // })

    // const matchingNames = computed(()=>{
    //   return names.value.filter((name)=>name.includes(search.value))
    // })

    // const handleClick = ()=>{
    //   stopWatch()
    //   stopWatchEffect()
    // }

    //  return { names, search, matchingNames, handleClick }

// ----------------------------------------------------------------//
//     const userOne = ref({name: 'mario', age: 30})
//     const userTwo = reactive({name:'luigi', age: 35})

//     const nameOne = ref('mario')
//     const nameTwo = reactive('luigi')

//   const updateUserOne=()=>{
//     userOne.value.age = 40
//   }

// // reactive does not perform well with primitive values instead prefer ref's over reactive
//   const updateUserTwo=()=>{
//     userTwo.age = 45
//     nameTwo = reactive('mario')
//   }

//     return{userOne, updateUserOne, userTwo, updateUserTwo, nameOne, nameTwo}

// ----------------------------------------------------------------//
      // const p = ref(null)
    // console.log("just after ref",p,p.value)

    // reactive values
    // const name = ref('mario');
    // const age = ref(30);

    
    // const handleClick=()=>{
    //   // console.log('you clicked me and logging ref on click',p, p.value)
    //   // p.value.classList.add('test')
    //   // p.value.textContent = 'hello, bros'
    //   name.value = 'luigi'
    //   age.value= 35
    // }

    // return { name,age, handleClick}
  },

}
</script>
