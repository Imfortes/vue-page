<template>
    <select name="sub-rubrics" id="subRubrics">
        <option value="Category" v-for="(subRubric, index) in subRubrics" :key="index">{{subRubric}}</option>
    </select>
</template>

<script>
    export default {
        data(){
            return{
                subRubrics: [
                    'Любая подрубрика',
                    'Любая подрубрика 1',
                    'Любая подрубрика 2',
                    'Любая подрубрика 3',
                    'Любая подрубрика 4',
                    'Любая подрубрика 5',
                    'Любая подрубрика 6',
                    'Любая подрубрика 7',
                    'Любая подрубрика 8',
                    'Любая подрубрика 9'
                ]
            }
        }
    }
</script>

<style>
    #subRubrics{
        width: 197px;
        height: 40px;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        padding: 8px 8px 8px 24px;
        appearance: none;
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat center right;
        background-color: #fff;
    }
</style>