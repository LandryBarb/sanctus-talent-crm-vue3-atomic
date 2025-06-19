<template>
    <main class="design-system">
        <h1>Design System</h1>
        <section class="ds-section">
            <h2>buttons</h2>
            <div class="ds-row">
                <BaseButton>Primary</BaseButton>
                <BaseButton variant="secondary">Secondary</Basebutton>
                <BaseButton variant="danger">Danger</BaseButton>
                <BaseButton variant="Disabled">Disabled</BaseButton>
               

            </div>
        </section>

        <!-- Add other sections here -->
    </main>
</template>

<script setup>
import BaseButton from '@/components/atoms/BaseButton.vue'
</script>


<style scoped>
.design-system{
    padding: 2rem;
    background-color: var(--bg-surface);
    color: var(--text-default);
}

.ds-section{
    margin-block-end: 3rem;
}

.ds-row{
    display: flex;
    gap:1rem;
    flex-wrap: wrap ;
}
</style>