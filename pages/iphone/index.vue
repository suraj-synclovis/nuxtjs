<template>
    <div class="allphones">
        <NuxtLink to="iphone/iphone-13-mini" class="card">
            <h1>Iphone 13 mini</h1>
            <div class="phones">
                <img width="200" src="/images/iphone-13-mini.webp" alt="" />
            </div>
        </NuxtLink>
        <NuxtLink to="/iphone/iphone-13" class="card">
            <h1>Iphone 13</h1>
            <div class="phones">
                <img width="200" src="/images/iphone-13.webp" alt="" />
            </div>
        </NuxtLink>
        <NuxtLink to="/iphone/iphone-14-pro" class="card">
            <h1>Iphone 14 Pro</h1>
            <div class="phones">
                <img width="200" src="/images/iphone-14-pro.webp" alt="" />
            </div>
        </NuxtLink>
        <NuxtLink to="/iphone/iphone-14-pro-max" class="card">
            <h1>Iphone 14 Pro Max</h1>
            <div class="phones">
                <img width="200" src="/images/iphone-14-pro-max.webp" alt="" />
            </div>
        </NuxtLink>
    </div>
</template>

<style>
.allphones {
    margin-top: 1rem;
    display: flex;
    gap: 2rem;
}

.card {
    padding: 2rem 4rem;
    text-align: center;
    box-shadow: 0px 2px 9px #0000001a;
    border-radius: 22px;
    text-decoration: none;
    color: #000;
}
</style>

<script setup>
useHead({
    title: "Nuxt3 - Iphones"
})
</script>