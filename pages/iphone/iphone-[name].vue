<template>
    <div>

        <Head>
            <Title>Nuxt 3- Iphone {{ name }}</Title>
        </Head>
        <div class="shop-phone">
            <div class="shop">
                <div>
                    <img :src="`/images/iphone-${route.params.name}.webp`" />
                </div>
                <div class="buy-button">
                    <h1>Iphone {{ name }}</h1>
                    <button @click="addToCart()" class="buy">
                        <span v-if="isInCart()">Remove from cart</span>
                        <span v-else>Buy Now</span>
                    </button>
                </div>
            </div>
        </div>
    </div>
</template>


<style>
.shop-phone {
    display: flex;
    justify-content: center;
    width: 100%;
    margin-top: 20px;
}

.shop {
    display: grid;
    grid-column: 2;
}

.buy-button {
    text-align: center;
}

.buy {
    background-color: indigo;
    color: white;
    border-radius: 6px;
    padding: 1rem 3rem;
    font-size: 14px;
    cursor: pointer;
}
</style>


<script setup>

const route = useRoute();

const name = computed(() => {
    return route.params.name.replaceAll('-', " ");
});

const fullname = computed(() => {
    return `iphone-${route.params.name}`;
});

useHead({
    title: `Nuxt3 - Iphone ${route.params.name}`
})

const cart = useCart();

function isInCart() {
    return !!cart.value.find((ct) => ct.name === fullname.value)
}

function addToCart() {

    if (!isInCart()) {
        cart.value.push({ name: fullname });
    } else {
        cart.value = cart.value.filter((ct) => ct.name !== fullname.value)
    }
}

</script>