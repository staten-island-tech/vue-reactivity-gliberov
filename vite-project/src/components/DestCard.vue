<template>
    <div>
<h2>{{  Destination.name }}</h2>
<img :src="Destination.img" alt="" />
<h3>{{ clicked }}</h3>
<button @clicked="increment">Click Me</button>
    </div>
</template>

<script setup>
import { ref } from "vue"
    const props = defineProps({
        Destination: object,
    });

    const clicked = ref(0)
    function increment() {
        clicked.value++
    }
</script>

<style lang="scss" scoped>

</style>