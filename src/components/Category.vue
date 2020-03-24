<template>
    <section class="category container">
        <header>
            <h3>Популярные рубрики</h3>
            <form action="">
                <label for="show-all">Показать все</label>
                <input type="checkbox" class="show-all radio" id="show-all" v-on:change="display=!display">
            </form>
        </header>

        <ul class="category-list">
            <li class="category-list__item">
                <span></span>
                Автосервис
            </li>
            <li class="category-list__item">
                <span></span>
                Безопасность
            </li>
            <li class="category-list__item">
                <span></span>
                Жилье и дом
            </li>
            <li class="category-list__item">
                <span></span>
                Бизнес
            </li>
            <li class="category-list__item">
                <span></span>
                Еда и напитки
            </li>
            <li class="category-list__item">
                <span></span>
                Здоровье и фитнес
            </li>



            <li class="category-list__item" v-show="display">
                <span></span>
                Автосервис
            </li>
            <li class="category-list__item" v-show="display">
                <span></span>
                Безопасность
            </li>
            <li class="category-list__item" v-show="display">
                <span></span>
                Жилье и дом
            </li>
            <li class="category-list__item" v-show="display">
                <span></span>
                Бизнес
            </li>
            <li class="category-list__item" v-show="display">
                <span></span>
                Еда и напитки
            </li>
            <li class="category-list__item" v-show="display">
                <span></span>
                Здоровье и фитнес
            </li>
        </ul>

    </section>
</template>

<script>
    export default {
        data(){
            return{
                display: false
            }
        }
    }
</script>

<style>
    .category{
        width: 100vw;
        height: 768px;
        background-color: #fff;
        padding-top: 50px;
    }
    .container{
        width: 1140px;
        margin: 0 auto;
    }
    header{
        display: flex;
        justify-content: space-between;
        align-items: center;
    }
    .category-list{
        list-style: none;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
    }
    .category-list span{
        width: 48px;
        height: 48px;
        background-color: #BDBDBD;
        box-sizing: border-box;
        display: block;
        -webkit-border-radius: 50%;
        -moz-border-radius: 50%;
        border-radius: 50%;
        margin-right: 15px;
    }
    .category-list__item{
        width: 30%;
        margin-top: 15px;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: flex-start;
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat center right;
        font-size: 22px;
        color: #2B4F6F;
    }
    .category form{
        display: flex;
        flex-direction: row;
        align-items: center;
    }
    input[type='checkbox'] {
        margin-left: 10px;
        position: relative;
        width: 24px;
        height: 12px;
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
        outline: none;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        transition: .5s;
        box-shadow: inset 0 0 5px rgba(0, 0, 0, .2);
    }
        input:checked [type = 'checkbox' ]{
        background: #C3C3C3;
    }
    input[type='checkbox']:before {
        content: '';
        position: absolute;
        width: 12px;
        height: 12px;
        background: #ffffff;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        top: 0;
        left: 0;
        transform: scale(1.1);
        box-shadow: 0 2px 5px rgba(0, 0, 0, .2);
        transition: .5s;
    }
    input:checked[type='checkbox']:before {
        left: 12px;
        background: #C3C3C3;
    }
    form label{
        font-size: 14px;
        color: #000;
    }
</style>