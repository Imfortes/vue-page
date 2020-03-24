<template>
    <select name="rubrics" id="selectRubrics" @mouseenter="showDropdown">
        <option value="Category" v-for="(rubric, index) in rubrics" :key="index">{{rubric}}</option>
    </select>
</template>

<script>
    export default {
        data(){
            return{
                rubrics: [
                    'Любая рубрика',
                    'Любая рубрика 1',
                    'Любая рубрика 2',
                    'Любая рубрика 3',
                    'Любая рубрика 4',
                    'Любая рубрика 5',
                    'Любая рубрика 6',
                    'Любая рубрика 7',
                    'Любая рубрика 8'
                ],
            }
        },
        methods: {
            showDropdown(element) {
                var event;
                event = document.createEvent('MouseEvents');
                event.initMouseEvent('mousedown', true, true, window);
                element.dispatchEvent(event);
            }
        }
    }
</script>

<style>
    #selectRubrics{
        width: 180px;
        height: 40px;
        -webkit-border-radius: 20px;
        -moz-border-radius: 20px;
        border-radius: 20px;
        padding: 8px 8px 8px 24px;
        border: none;
        appearance: none;
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat center right;
        background-color: #fff;
        position: relative;
    }


    #selectRubrics option:hover{
        display: block;
    }
    option{
        height: 40px;
        border: none;
        outline: none;
    }
</style>