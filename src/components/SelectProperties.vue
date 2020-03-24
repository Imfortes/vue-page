<template>
    <select name="properties" id="selectProperties">
        <option value="Category" v-for="(props, index) in selectProperties" :key="index">{{props}}</option>
    </select>
</template>

<script>
    export default {
        data(){
            return{
                selectProperties: [
                    'Доп. параметры',
                    'Рейтинг',
                    'Отзывы',
                    'Алфавит'
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
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat center right;
        background-color: #fff;
    }
    option{
        height: 40px;
    }
    option:last-child{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }
</style>