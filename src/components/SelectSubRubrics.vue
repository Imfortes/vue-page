<template>
<!--    <select name="sub-rubrics" id="subRubrics">-->
<!--        <option value="Category" v-for="(subRubric, index) in subRubrics" :key="index">{{subRubric}}</option>-->
<!--    </select>-->

    <div class="sub-rubrics" id="subRubrics">
        <p
                class="sub-rubrics__checked"
                @click="areOptionsVisible = !areOptionsVisible"
        >Подрубрика</p>
        <div class="sub-rubrics__option"
             v-if="areOptionsVisible"
        >
            <p
                    v-for="(subRubric, index) in subRubrics"
                    :key="index"
            >
                {{subRubric}}
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
        },
        directives: {
            clicked: {
                update: function (el) {
                    el.style.borderRadius = '20px 20px 0 0'
                }
            }
        }
    }
</script>

<style >
    #subRubrics{
        position: relative;
        z-index: 100;
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
    #subRubrics p{
        font-size: 13.3333px;
        height: 100%;
        color: #2B4F6F;
        cursor: pointer;
        display: flex;
        align-items: center;
    }
    #subRubrics .sub-rubrics__option{
        position: absolute;
        top: 40px;
        left: 0;
        width: 197px;
    }

    #subRubrics:hover,
    #subRubrics:active{
        background: #fff;
        color: #000;
        background: url("../assets/ic_expand_more_black_18px.png") no-repeat center right;
        background-color: #fff;
        -webkit-border-radius: 20px 20px 0 0;
        -moz-border-radius: 20px 20px 0 0;
        border-radius:  20px 20px 0 0;
    }
    #subRubrics p:hover{
        color: #4BBAC5;

    }
    .sub-rubrics__option p{
        height: 40px;
        width: 197px;
        background: #fff;
        color: #000;
        padding: 8px 8px 8px 24px;
    }
    #subRubrics p:active{
        color: #000;
        background: #fff;
    }
    .sub-rubrics__option p:last-child{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }
    .sub-rubrics__option p:last-child:hover{
        -webkit-border-radius: 0 0 20px 20px;
        -moz-border-radius: 0 0 20px 20px;
        border-radius: 0 0 20px 20px;
    }
    .options p:hover{
        color: #4BBAC5;
    }

</style>