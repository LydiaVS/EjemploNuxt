<template>
    <img class="banner-image" :src="source" :alt="alt">
</template>

<script>
export default {
    props:['source','alt']
}
</script>

<style lang="postcss">
    .banner-image{
        @apply w-full;
    }

</style>