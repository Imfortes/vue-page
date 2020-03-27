<template>
    <main class="main">

        <div class="main-title container">
            <h1>Онлайн запись в сфере услуг</h1>
            <span>#просто_быстро_для_вас</span>
        </div>

        <div class="container form__wrap">

            <input type="search" placeholder="Поиск компаний и услуг" class="search-input">

            <SelectProperties></SelectProperties>

            <SelectRubrics v-bind="areOptionsVisible"></SelectRubrics>

            <SelectSubRubrics v-bind="areOptionsVisible"></SelectSubRubrics>


            <button class="search-btn">Найти</button>

            <button class="search-btn-map">На карте</button>
            
        </div>

        <div class="container description-list">
            <div class="description-item">
                <img src="../assets/1.png" alt="">
                <div>
                    <b>90 000</b>
                    <br>
                    <span>компаний</span>
                </div>
            </div>

            <div class="description-item">
                <img src="../assets/2.png" alt="">
                <div>
                    <b>560 000</b>
                    <br>
                    <span>специалистов <br> и мастеров</span>
                </div>
            </div>

            <div class="description-item">
                <img src="../assets/3.png" alt="">
                <div>
                    <b>2 млн</b>
                    <br>
                    <span>клиентов</span>
                </div>
            </div>

            <div class="description-item">
                <img src="../assets/4.png" alt="">
                <div>
                    <b>10 000</b>
                    <br>
                    <span>записей <br> ежедневно</span>
                </div>
            </div>

            <div class="description-item">
                <img src="../assets/5.png" alt="">
                <div>
                    <b>45 000 </b>
                    <br>
                    <span>отзывов</span>
                </div>
            </div>
        </div>

    </main>
</template>

<script>
import SelectProperties from './SelectProperties.vue';
import SelectRubrics from './SelectRubrics.vue';
import SelectSubRubrics from './SelectSubRubrics.vue';

export default {
    components: {
        SelectProperties,
        SelectRubrics,
        SelectSubRubrics
    }
}
</script>

<style>
    .main{
        width: 100vw;
        height: 576px;
        background: url("../assets/star.png");
    }
    .container{
        width: 1140px;
        margin: 0 auto;
    }
    .main-title{
        width: 100%;
        padding-top: 60px;
    }
    .main-title h1{
        font-size: 32px;
        color: #263548;
    }
    .main-title span{
        color: #ffffff;
        font-size: 20px;
    }
    .search-input{
        outline: none;
        border: none;
    }
    .form__wrap,
    .description-list{
        padding-top: 80px;
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        align-items: center;
    }
    .description-list{
        padding-top: 60px;
    }
    .description-item{
        height: 150px;
        display: flex;
        flex-direction: column;
        justify-content: flex-start;
        align-items: center;
        text-align: center;
        color: #ffffff;
    }
    .description-item div{
        margin-top: 35px;
    }
    .description-item b{
        font-size: 20px;
    }
    .description-item span{
        color: #B7E3E8;
    }
    .description-item img{

    }
    .search-input{
        width: 250px;
        height: 40px;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        padding: 8px 8px 8px 24px;
    }
    .search-btn{
        text-transform: uppercase;
        width: 102px;
        height: 40px;
        border: none;
        color: rgba(255, 255, 255, .6);
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        background-color: #263548;
        outline: none;
        cursor: pointer;
    }
    .search-btn-map{
        text-transform: uppercase;
        width: 121px;
        height: 40px;
        border: none;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        background-color: #B7E3E8;
        color: #263548;
        outline: none;
        cursor: pointer;
    }
</style>