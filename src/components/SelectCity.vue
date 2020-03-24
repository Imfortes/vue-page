<template>
    <select name="citiesTitle" id="" >
        <option
                v-for="(city, index) in cities"
                v-bind:value="city"
                :key="index">{{city}}
        </option>
    </select>
</template>

<script>
    export default {
        props: {
            cities: {
                type: Array
            }
        },
    }
</script>

<style>
    select{
        background: none;
        border: none;
        outline: none;
        appearance: none;

    }
</style>