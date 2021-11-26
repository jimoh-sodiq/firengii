<template>
    <div class="text-black mt-4">
        <MyItem 
            v-for="item in myRentals" :key ="item.id"
            :item='item'
        />
    </div>
</template>

<script>
import {mapState, mapMutations} from 'vuex';
    export default {
        layout: 'no-nav',
        computed: {
            ...mapState([
                'myRentals'
            ]), mapMutations
        }
    }
</script>

<style scoped>

</style>