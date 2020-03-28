<template>
    <ul class="category-list">
        <li class="category-list__item"
            v-for="(categoryItem, index) in categoryListItem.slice(0, 6)"
            :key="index"
        >
            <span></span>
            {{ categoryItem }}
        </li>
    </ul>
</template>

<script>




    export default {
        data(){
            return {
                categoryListItem: [
                    'Автосервис',
                    'Безопасность',
                    'Жилье и дом',
                    'Бизнес',
                    'Еда и напитки',
                    'Здоровье и фитнес',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                    'Другие категории',
                ]
            }
        },
        computed: {
            showList: () => {
                return this.categoryListItem.filter(function (categoryItem) {
                    return categoryItem.slice(6, )
                })
            }
        }
    }
</script>

<style>
    .category-list{
        list-style: none;
        display: flex;
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: space-around;
        align-items: center;
    }
</style>