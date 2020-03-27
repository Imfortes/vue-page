<template>
  <header class="header">
    <div class="space"></div>
    <nav class="navbar">

      <div class="navbar__wrap">
        <img src="../assets/ic_access_location_top.png" alt="">
        <SelectCity
                v-bind:cities="cities"
                @select="optionSelect"
        ></SelectCity>
      </div>

      <div class="navbar__wrap">
        <img src="../assets/ic_local_phone_top.png" alt="">
        <a href="tel:88001234567">8 (800) 123 45 67</a>
      </div>

      <div class="navbar__wrap">
        <img src="../assets/ic_exit_top.png" alt="">
        <a href="#" @click="showModal">Вход</a>
      </div>

      <div class="navbar__wrap">
        <img src="../assets/ic_register_top.png" alt="">
        <a href="#" @click="showModal">Регистрация</a>
      </div>

    </nav>

    <div
            class="popup-wrap"
            v-show="isModalVisible"
            @close="closeModal"
    >
      <div class="popup">
        <header class="popup__header">
          <h2>Вход</h2>
          <img src="../assets/ic_clear.png" alt="" @click="closeModal">
        </header>

        <section class="popup__tabs">
          <div class="popup__tabs-phone">
            <a href="#" class="popup__tabs-link popup__tabs-link-active" v-bind="active" v-if="active">Телефон</a>
          </div>
          <div class="popup__tabs-email">
            <a href="#" class="popup__tabs-link">E-mail</a>
          </div>
        </section>

        <section class="popup__main-phone">
          <p class="popup__main-phone--decr">
            На указанный номер телефона будет выслан код для авторизации
          </p>
          <input type="text" class="popup__main-phone--input" placeholder="+7 (___) ___ - __ - __">
          <input type="submit" class="popup__main-phone--submit">
        </section>

        <section class="popup__confidencial">
          <p>
            Авторизуясь, вы соглашаетесь с
            <a href="">Правилами и Политикой конфиденциальности</a>
          </p>
        </section>

        <footer class="popup__footer">
            <span>Еще нет аккаунта?</span>
            <a href="#">Зарегистрируйтесь</a>
        </footer>

      </div>
    </div>

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
    data(){
      return{
        selected: '',
        display: false,
        isModalVisible: false,
        active: true
      }
    },
    components: {
      SelectCity
    },
    methods: {
      optionSelect(city){
        console.log(this);
        this.selected = city
      },
      showModal(){
        this.isModalVisible = true;
        console.log(this);
        console.log(this.isModalVisible)
      },
      closeModal(){
        this.isModalVisible = false
      }
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
    margin: 0 10px 0 0;
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
  header select {
    min-width: 140px;
  }


  .popup-wrap{
    position: fixed;
    top: 0;
    left: 0;
    overflow-x: hidden;
    z-index: 10000;
    background-color: #fff;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;

  }
  .popup{
    width: 328px;
    height: 440px;
    -webkit-box-shadow: 0 3px 5px 0 rgba(50, 50, 50, 0.75);
    -moz-box-shadow:    0 3px 5px 0 rgba(50, 50, 50, 0.75);
    box-shadow:         0 3px 5px 0 rgba(50, 50, 50, 0.75);
  }
  .popup header{
    padding: 10px 10px 0 10px;
  }
  .popup h2{
    font-size: 28px;
    font-weight: 400;
  }
  .popup__tabs{
    width: 100%;
    display: flex;
    flex-direction: row;
    padding-top: 30px;
  }
  .popup__tabs-phone,
  .popup__tabs-email{
    width: 50%;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  .popup__tabs-link{
    text-align: center;
    width: 100%;
    font-size: 14px;
    font-weight: bold;
    color: #707070;
    text-decoration: none;
    text-transform: uppercase;
    border-bottom: 2px solid #707070;
    padding-bottom: 10px;
    transition: 1s;
  }
  .popup__tabs-link:hover,
  .popup__tabs-link-active{
    color: #6845C6;
    border-color: #6845C6;
  }
  .popup__main-phone{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding-top: 30px;
  }
  .popup__main-phone--decr{
    width: 250px;
    text-align: center;
    font-size: 14px;
  }
  .popup__main-phone--input{
    width: 250px;
    outline: none;
    border: none;
    padding: 5px 10px;
    margin-top: 30px;
    border-bottom: 1px solid #707070;
  }
  .popup__main-phone--submit{
    width: 280px;
    height: 36px;
    margin-top: 30px;
    border: none;
    outline: none;
    background-color: #4BBAC5;
    border: 1px solid #ffffff;
    color: #ffffff;
    -webkit-border-radius: 20px;
    -moz-border-radius: 20px;
    border-radius: 20px;
    cursor: pointer;
    transition: .5s;
  }
  .popup__main-phone--submit:hover{
    color: #4BBAC5;
    background-color: #fff;
    border: 1px solid #4BBAC5;
  }
  .popup__confidencial{
    font-size: 12px;
    width: 280px;
    margin: 0 auto;
    margin-top: 30px;
    text-align: center;
  }
  .popup__footer{
    font-size: 14px;
    width: 280px;
    margin: 0 auto;
    margin-top: 30px;
    display: flex;
    justify-content: space-between;
  }
  .popup__confidencial a,
  .popup__footer a{
    color: #5A7B9D;
  }
  .popup__confidencial a:hover,
  .popup__footer a:hover{
    color: #4BBAC5;
  }


</style>
