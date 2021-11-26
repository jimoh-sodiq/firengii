<template>
    <div>
        <div v-if="product" class="container pt-16 w-3/4 mx-auto md:w-3/5">
            <div class="hero-container mb-8 relative">
                <img :src="require(`~/assets/images/${product.image}`)" alt="" class="image">
                <div class="info-box">
                    <h1 class="md:text-4xl">{{ product.title }}</h1>
                    <p class="snippet md:text-lg">
                        {{ product.snippet }}
                    </p>
                    <div>
                        <RentButton :product='product' />
                    </div>
                </div>
            </div>
            <div class="whats-included-container">
                <div class="included-container mb-4">
                    <h6>Super Effective</h6>
                    <p> lorem ipsum dolor sit amet consectetur adipiscing elit, Asperiores, dolorem </p>
                </div>
                <div class="included-container mb-4">
                    <h6>Clean & tidy</h6>
                   <p> lorem ipsum dolor sit amet consectetur adipiscing elit, Asperiores, dolorem </p>
                </div>
                <div class="included-container mb-4">
                    <h6>Cancel Anytime</h6>
                   <p> lorem ipsum dolor sit amet consectetur adipiscing elit, Asperiores, dolorem </p>
                </div>
                <div class="included-container mb-8">
                    <h6>Satisfaction Guaranteed</h6>
                   <p> lorem ipsum dolor sit amet consectetur adipiscing elit, Asperiores, dolorem </p>
                </div>
            </div>
            <div class="description-container">
                <p>{{product.description}}</p>
            </div>
            <Reviews />
        </div>
        <div class="container padding" v-else>
            <PageNotFound />
        </div>
    </div>
</template>

<script>
import {mapGetters} from 'vuex'
    export default {
        computed: {
            ...mapGetters([
                'getProducts'
            ]),

            product() {
                return this.getProducts(this.$route.params.id)
                }
            
    },

}
</script>

<style scoped>

p {
    color: grey
}

.snippet {
    color: rgba(0, 0, 0.774);
    margin-top: 1rem;
}

button {
    width: 100%;
    border: none;
    padding: 0.5rem;
    color: white;
    font-weight: 700;
    padding: 1rem 4rem;
    border-radius: 10rem;
    background-color: rgb(231, 81, 43);
    transition: 0.5s;
}

.description-container {
    margin-top: 2rem;
    color: grey;
    margin-bottom: 2rem;
    padding-bottom: 2rem;
    border-bottom:  0.1rem solid rgba(128, 128, 128, 0.151);
}
.padding {
    padding: 10rem 0;
}
.hero-container{
    display: flex;
    justify-content: space-between;
}
h6{ 
    font-size: 1.15rem;
    font-weight: 400;
}
h1{ 
    font-size: 1.75rem;
}

.image {
    width: 50%;
    height: 20rem
}
.info-box {
    width: 39%;
    background-color: rgba(207, 201, 201, 0.3222);
    padding: 1rem;
    border-radius: 0.5rem;
}

.whats-included-container{
    border-bottom: 0.1rem solid rgba(128, 128, 128, 0.151)
}
</style>