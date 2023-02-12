<script setup>
    export default {
        created: {
            fetch();
        },

        data() {
            return {
                listClass: "list-class"
            },
        },

        methods: {
            fetch(){

            }
        }
    };
</script>

<template>
    <section :class="listClass"></section>
</template>

<style scoped>
    .list-class {
        background-color: red;
    }
</style>