<template>
    <div>

        <div name="properties" id="selectProperties" @click="areOptionsVisible = !areOptionsVisible">
            <p value="Category" v-for="(props, index) in selectProperties" :key="index">{{props}}</p>
        </div>

        <section class="properties-list"  v-if="areOptionsVisible">
            <header class="properties-list__radio">

                <input type="checkbox" class="rating" id="rating">
                <label for="rating">Рейтинг</label>

                <input type="checkbox" class="reviews" id="reviews">
                <label for="reviews">Отзывы</label>

                <input type="checkbox" class="alphabet" id="alphabet">
                <label for="alphabet">Алфавит</label>


            </header>

            <section class="properties-list__tabs">
                <div class="properties-list__tabs-item">
                    <img src="../assets/ic_local__activ.png" alt="">
                    Локация
                </div>
                <div class="properties-list__tabs-item">
                    <img src="../assets/ic_data.png" alt="">
                    Дата и время
                </div>
                <div class="properties-list__tabs-item">
                    <img src="../assets/ic_balance.png" alt="">
                    Цена
                </div>
            </section>

            <footer class="properties-list__footer">
                <button class="properties-list__footer-clean">Сбросить</button>
                <button class="properties-list__footer-search">Найти</button>
            </footer>

        </section>

    </div>

</template>

<script>
    export default {
        props: {
            areOptionsVisible: {
                type: Boolean
            }
        },
        data(){
            return{
                selectProperties: [
                    'Доп. параметры',
                ],
            }
        }
    }
</script>

<style>
    #selectProperties{
        width: 180px;
        height: 40px;
        padding: 8px 10px 8px 24px;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        appearance: none;
        background: url("../assets/ic_dop param.png") no-repeat 95% 50%;
        background-color: #fff;
        position: relative;
    }
    #selectProperties p {
        font-size: 13.3333px;
        height: 100%;
        color: #2B4F6F;
        cursor: pointer;
        display: flex;
        align-items: center;
    }
    option{
        height: 40px;
    }
    option:last-child{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }

    .properties-list{
        width: 360px;
        padding: 20px 10px;
        position: absolute;
        top: 43px;
        left: -50%;
        background-color: #fff;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        z-index: 100;
    }
    .properties-list__tabs{
        display: flex;
        flex-direction: row;
        justify-content: space-around;
        padding-top: 30px;
        padding-bottom: 30px;
    }
    .properties-list__tabs-item{
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        font-size: 14px;
        color: rgba(0, 0, 0, .68);
    }

    .properties-list input[type='checkbox'] {
        margin-left: 10px;
        position: relative;
        width: 34px;
        height: 14px;
        -webkit-appearance: none;
        -moz-appearance: none;
        appearance: none;
        outline: none;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        transition: .5s;
        box-shadow: inset 0 0 5px rgba(0, 0, 0, .2);
        background: rgba(0, 0, 0, 0.2);
    }
    .properties-list input:checked[type = 'checkbox']{
        background: #A4DCE1;
    }
    .properties-list input[type='checkbox']:before {
        content: '';
        position: absolute;
        width: 17px;
        height: 14px;
        background: #F1F1F1;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        top: 0;
        left: 0;
        transform: scale(1.1);
        box-shadow: 0 2px 5px rgba(0, 0, 0, .2);
        transition: .5s;
    }
    .properties-list input:checked[type='checkbox']:before {
        left: 17px;
        background: #4BBAC5;
    }

    .properties-list__footer{
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
    }
    .properties-list__footer-clean,
    .properties-list__footer-search{
        font-size: 14px;
        color: rgba(0, 0, 0, .6);
        background: none;
        outline: none;
        border: none;
        text-transform: uppercase;
        cursor: pointer;
        transition: .5s;
    }
    .properties-list__footer-clean:hover{
        color: #4BBAC5;
    }

    .properties-list__footer-search{
        color: #4BBAC5;
    }
    .properties-list__footer-search:hover{
        color: rgba(0, 0, 0, .6);
    }

</style>