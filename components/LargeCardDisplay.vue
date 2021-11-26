<template>
<div>
    <div class="mt-8" v-for="items in LargeCardSections" :key="items.id">
        <h4 class="font-semibold uppercase">
            {{
                items.title
            }}
        </h4>
        <p class="text-black mb-6">{{items.snippet}}</p>
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3">
            <LargeCard  v-for="card in items.cards " :key="card.id" class="mr-4 w-100">
                <nuxt-link :to="`/products/${card.id}`">
                    <img :src="require(`@/assets/images/${card.image}`)" alt="" class="w-full h-24 mb-4 cursor-pointer hover:opacity-80 ">
                    <h3 class="font-semibold text-sm underline capitalize">
                        {{ card.title }}
                    </h3>
                    <p class="text-sm">
                        {{ card.snippet }}
                    </p>
                </nuxt-link>
            </LargeCard>
        </div>
    </div>
</div>
    
</template>

<script>
import { mapState } from 'vuex';
    export default {
        computed: {
            ...mapState([
                'LargeCardSections'
            ])
        }
    }
</script>

<style scoped>

</style>