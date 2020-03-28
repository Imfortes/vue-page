<template>
    <header
            class="subheader"
            :class="{ 'subheader--hidden' : !showSubheader }"
            v-show="display"
    >
         Ваш город -  <span> Екатеринбург?</span>
        <a href="#" @click="display = false">Да</a>
        <SelectCity v-bind:cities="cities" v-model="selected">
            <option value="" slot="subHeaderDefault">Изменить город</option>
        </SelectCity>
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
                selected: 'Изменить город',
                showSubheader: true,
                lastScrollPosition: 0
            }
        },
        mounted() {
            window.addEventListener('scroll', this.onScroll)
        },
        beforeDestroy () {
            window.removeEventListener('scroll', this.onScroll)
        },
        methods: {
            onScroll() {

                const currentScrollPosition = window.pageYOffset || document.documentElement.scrollTop;

                if (currentScrollPosition < 0) {
                    return
                }
                if (Math.abs(currentScrollPosition - this.lastScrollPosition) < 0) {
                    return
                }

                this.showSubheader = currentScrollPosition < this.lastScrollPosition;
                this.lastScrollPosition = currentScrollPosition;
            }
        }
    }
</script>

<style>
    .subheader{
        overflow-x: hidden;
        width: 100vw;
        height: 44px;
        background-color: #fff;
        display: flex;
        justify-content: center;
        align-items: center;
        position: fixed;
        top: 90px;
        left: 0;
        z-index: 100;
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
    .subheader--hidden {
        display: none;
    }
    subheader .select-city option{
        position: relative;
        z-index: 100;
    }

</style>