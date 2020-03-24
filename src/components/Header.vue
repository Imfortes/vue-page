<template>
  <header class="header">
    <div class="space"></div>
    <nav class="navbar">

      <div class="navbar__wrap">
        <img src="../assets/ic_access_location_top.png" alt="">
        <SelectCity v-bind:cities="cities"></SelectCity>
      </div>

      <div class="navbar__wrap">
        <img src="../assets/ic_local_phone_top.png" alt="">
        <span>8 (800) 123 45 67</span>
      </div>

      <div class="navbar__wrap">
        <img src="../assets/ic_exit_top.png" alt="">
        <a href="#">Вход</a>
      </div>

      <div class="navbar__wrap">
        <img src="../assets/ic_register_top.png" alt="">
        <a href="#">Регистрация</a>
      </div>

    </nav>
  </header>
</template>

<script>
  import SelectCity from './SelectCity.vue';

  export default {
    name: 'Header',
    props: {
      cities: {
        type: Array
      }
   },
    components: {
      SelectCity
    }
  }
</script>


<style scoped>
  a{
    text-decoration: none;
  }
  .header{
    background-color: #263548;
    width: 100vw;
    height: 90px;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
  }
  .space,
  .navbar{
    width: 50%;
    display: flex;
    align-items: center;
    justify-content: flex-start;
  }
  .navbar__wrap,
  .navbar__wrap a{
    display: flex;
    align-items: center;
    margin: 0 20px 0 0;
    color: rgba(255, 255, 255, .6);
  }
  .navbar__wrap img{
    margin-right: 10px;
  }
  header select{
    background: url("../assets/ic_expand_more_black_18px.png") no-repeat center right;
    color: rgba(255, 255, 255, .6);
    background-color: #263548;
  }
</style>
