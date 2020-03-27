<template>
<!--    <select name="citiesTitle" id="" >-->
<!--        <slot name="subHeaderDefault"></slot>-->
<!--        <option-->
<!--                v-for="(city, index) in cities"-->
<!--                v-bind:value="city"-->
<!--                :key="index">{{city}}-->
<!--        </option>-->
<!--    </select>-->

    <div class="select-city">
        <p class="title"
            @click="areOptionsVisible = !areOptionsVisible"
        >Екатеринбург</p>
        <div class="options"
            v-if="areOptionsVisible"
        >
            <p
                    class="option-val"
                    v-for="city in cities"
                    v-bind:value="city.name"
                    :key="city.value"
                    @click="selectOption()"
            >
                {{city.name}}
            </p>
        </div>
    </div>

</template>

<script>
    export default {
        props: {
            cities: {
                type: Array
            },
            areOptionsVisible: {
                type: Boolean
            }
        },
        data(){
            return{

            }
        },
        methods: {
            selectOption(city){
                console.log(city);
                console.log(this);
                this.$emit('select', city)
            }
        }
    }
</script>

<style>
    select{
        background: none;
        border: none;
        outline: none;
        appearance: none;
        color: #2B4F6F;
        cursor: pointer;
    }
    .select-city{
        position: relative;
        min-width: 160px;
        margin: 0;
        cursor: pointer;
        height: 36px;
        display: flex;
        align-items: center;
        padding-left: 10px;
        -webkit-border-radius: 20px 20px 0 0;
        -moz-border-radius: 20px 20px 0 0;
        border-radius: 20px 20px 0 0;
        z-index: 1000;
    }
    .select-city:hover{
        background: #fff;
        color: #000;
    }
    .select-city p:hover{
        color: #4BBAC5;

    }
    .select-city:active{
        color: #000;
        background: #fff;
    }
    .options{
        position: absolute;
        top: 36px;
        right: 0;
        width: 100%;
        height: 36px;
    }
    .options p{
        height: 36px;
        padding-left: 10px;
        background: #fff;
        color: #000;
    }
    .option-val:last-child{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }
    .option-val:last-child:hover{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }
    .options p:hover{
        color: #4BBAC5;
    }

</style>