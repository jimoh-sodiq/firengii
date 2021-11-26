<template>
<div class="p-2 mb-8">
     <div class= "w-100 h-full ">
       <slot> </slot>
    </div>
</div> 
</template>

<script>
import{ mapState } from 'vuex';
    export default {
        computed : {
            ...mapState([
                'LargeCardSections'
            ])
        }
    }
</script>

<style scoped>

</style>