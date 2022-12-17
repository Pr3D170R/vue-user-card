<template>
  <UserCard v-bind:nickname="nickname" v-bind:fullname="fullname" v-bind:sity="sity" v-bind:stritn="stritn" v-bind:email="email" v-bind:number="number"/>
  <button v-on:click="getList()">get data</button>
</template>

<script>
import UserCard from './components/UserCard.vue';

export default {
  name: 'App',
  components: {
    UserCard
  },
  methods:{
    getList(){
      this.axios.get('https://randomuser.me/api/').then((response)=>{
        console.log(response.data)
      })
    }
  },
  data(){
    return {
      nickname: 'moryak',
      fullname: 'Василий Тёркин',
      sity: 'Москва',
      stritn: 'Юбилейная 50',
      email: 'coldrabbit48@example.com',
      number: '+7-495-266-57-34'
    }
  }
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
}
</style>
