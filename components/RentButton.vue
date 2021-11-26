<template>
    <div class="w-full m-auto mt-4 ">
        <button 
        @click="addItem(product.id)"
        class="w-full m-auto p-2  bg-red-500 rounded-full hover:opacity-80">Rent</button>
    </div>
</template>

<script> 
import {mapMutations} from 'vuex'
    export default {
        props: ['product'],
        methods: {
            ...mapMutations([
                'addItem'
            ])
        }
    }
</script>

<style scoped>
</style>