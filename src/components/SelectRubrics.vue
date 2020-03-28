<template>
<!--    <select name="rubrics" id="selectRubrics" @mouseenter="showDropdown">-->
<!--        <option value="Category" v-for="(rubric, index) in rubrics" :key="index">{{rubric}}</option>-->
<!--    </select>-->

    <div class="rubrics" id="selectRubrics">
        <p
                class="rubrics__checked"
                @click="areOptionsVisible = !areOptionsVisible"

        >Рубрика</p>
        <div class="rubrics__option"
             v-if="areOptionsVisible"
        >
            <p
                    v-for="(rubric, index) in rubrics"
                    :key="index"
            >
                {{rubric}}
            </p>
        </div>
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
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat 95% 50%;
        background-color: #fff;
        position: relative;
        z-index: 100;
    }


    #selectRubrics option:hover{
        display: block;
    }
    option{
        height: 40px;
        border: none;
        outline: none;
    }

    #selectRubrics p{
        font-size: 13.3333px;
        height: 100%;
        color: #2B4F6F;
        cursor: pointer;
        display: flex;
        align-items: center;
    }
    #selectRubrics .rubrics__option{
        position: absolute;
        top: 43px;
        left: 0;
        width: 180px;
    }

    #selectRubrics:hover,
    #selectRubrics:active{
        background: #fff;
        color: #000;
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat no-repeat 95% 50%;
        background-color: #fff;
    }
    #selectRubrics p:hover{
        color: #4BBAC5;
    }
    .rubrics__option p{
        height: 40px;
        width: 180px;
        background: #fff;
        color: #000;
        padding: 8px 8px 8px 24px;
    }
    #subRubrics p:active{
        color: #000;
        background: #fff;
    }
    .rubrics__option p:first-child{
        -webkit-border-radius: 20px 20px 0 0;
        -moz-border-radius: 20px 20px 0 0;
        border-radius: 20px 20px 0 0;
    }
    .rubrics__option p:last-child{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }
    .options p:hover{
        color: #4BBAC5;
    }
</style>