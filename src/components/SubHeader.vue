<template>
    <header class="subheader" v-if="display">
         Ваш город - <span> Екатеринбург?</span>
        <a href="#" @click="display = false">Да</a>
        <SelectCity v-bind:cities="cities" v-model="selected"></SelectCity>
    </header>
</template>

<script>
    import SelectCity from './SelectCity.vue';

    export default {
        props: {
            cities: {
                type: Array
            },

        },
        components: {
            SelectCity
        },
        data(){
            return{
                display: true,
                selected: 'Изменить город'
            }
        },
    }
</script>

<style>
    .subheader{
        width: 100vw;
        height: 44px;
        background-color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        position: fixed;
        top: 90px;
        left: 0;
    }
    .subheader a{
        color: #ffffff;
        text-decoration: none;
        background-color: #4BBAC5;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        padding: 0 10px;
        margin: 0 10px;
    }
    .fixed-top{
        bottom: 0;
    }

    .fixed-bottom{
        bottom: -75px;
    }
</style>