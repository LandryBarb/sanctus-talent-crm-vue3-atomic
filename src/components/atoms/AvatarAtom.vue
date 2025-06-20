<template>
    <figure class="avatar" :style="{ width: size + 'px', height: size + 'px'}" role="img" :aria-label="alt">
        <img v-if="src" :src="src" :alt="alt"/>
        <div class="avatar__fallback">{{ initials }}</div>
    </figure>
</template>

<script setup>
defineProps({
    src: String,
    alt: {
        type: String,
        default: 'User avatar'
    },
    initials:{
        type: String,
        default: ''
    },
    size:{
        type: Number,
        default: 40
    }
})
</script>