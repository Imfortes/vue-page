<template>
  <div id="app">
    <Header v-bind:cities="cities"></Header>
    <SubHeader v-bind:cities="cities" ></SubHeader>
    <Main v-bind="areOptionsVisible"></Main>
    <Category></Category>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import SubHeader from './components/SubHeader.vue'
import Main from './components/Main.vue'
import Category from './components/Category.vue'


export default {
  name: 'App',
  data(){
    return{
      cities: [
        {name: 'Москва', value: 1},
        {name: 'Санкт-Петербург', value: 2},
        {name: 'Нижний Новгород', value: 3}
      ],
      areOptionsVisible: false
    }
  },
  components: {
    Header,
    SubHeader,
    Main,
    Category,

  },

}
</script>

<style>
  *{
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Roboto, sans-serif;
    position: relative;
  }
</style>
