<template>
    <div>


        <button @click="moveToAbout">Take me to About</button>
        Hello Index
    </div>
</template>

<script setup>
function moveToAbout() {
    navigateTo("about")
}
</script>