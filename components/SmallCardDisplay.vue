<template>
    <div >
        <div class="py-8" v-for="items in SmallCardSection" :key="items.id">
            <h3 class="font-semibold text-lg uppercase mb-4">
            {{ items.title}}
            </h3>
            <div class="grid grid-cols-3 md:grid-cols-4 gap-4 overflow-hidden ">
                <SmallCard v-for="card in items.cards " :key="card.id" class="w-100">
                    <nuxt-link :to="`/products/${card.id}`" class="card-container">
                        <img class="image" :src="require(`@/assets/images/${card.image || 'fe1.jpg'}`)" alt="">
                    </nuxt-link>
                </SmallCard>
            </div>
        </div>
    </div>
</template>

<script>
import {mapState} from 'vuex';
    export default {
        computed: {
            ...mapState([
                'SmallCardSection'
            ])
        }
    }
</script>

<style scoped>
    .card-container {
        width: 24%;
        height: 12.5rem;
        border-radius: 0.5rem;
        overflow: hidden;
        margin-bottom: 1.5rem;
        cursor: pointer;
    }
    .image {
        width: 100%;
        height: 100%
    }
</style>