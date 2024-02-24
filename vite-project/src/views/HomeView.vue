<template>
    <div>
        <h1>Welcome to my Piano App (click the keys)</h1>
        <h2>EAR WARNING: YOU MIGHT NOT WANT TO PRESS CHORD WITH TOO MANY NOTES </h2>
        <Piano />
    </div>
</template>

<script>
import Piano from '@/components/Piano.vue';

    export default {
    components: { Piano }
}
</script>

<style lang="scss" scoped>

</style>
