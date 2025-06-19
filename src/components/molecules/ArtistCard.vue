<template>
    <article class="artist-card" aria-labelledby="artist-name">
        <header class="artist-card__header">
            <img 
            class="artist-card__photo"
            :src="photoUrl" 
            :alt="`Photo of ${name}`"
            loading="lazy" 
            >
            <h2 id="artist-name" class="artisy-card__name">
                {{ name }}
            </h2>
            <p class="artist-card__type" aria-label="Artist Category">
                {{ type }}
            </p>
        </header>

        <section class="artist-card__tags" aria-label="Artist Labels">
            <span
            v-for="label in labels"
            :key="label"
            class="artist-card__tag"
            >
            {{ label }}
            </span>
        </section>

        <footer class="artist-card__actions">
           
            <button class="artist-card__button"
            @click="$emit('view')"
            aria-label="View profil for {{ name }}"
            >
            view profile
            </button>
            <button class="artist-card__button"
            @click="$emit('edit')"
            aria-label="Edit profile for {{ name }}"
            >
            Edit
        </button>
        </footer>
    </article>
</template>
<script setup>

defineProps({
    name:{
        type: String,
        required: true
    },
    type:{
        type: String,
        required: true
    },
    photoUrl: {
        type: String,
        required: true
    },
    labels: {
        type: Array,
        default: () => []
    }
})

defineEmits(['view', 'edit'])
</script>
<style lang="scss">
.artist-card {
  background-color: #ffffff;
  border: 1px solid #e5e7eb;
  border-radius: 0.75rem;
  box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
  padding: 1rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;
  transition: box-shadow 0.2s ease-in-out;

  &:hover {
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  }

  &__header {
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    margin-bottom: 1rem;
  }

  &__photo {
    width: 96px;
    height: 96px;
    object-fit: cover;
    border-radius: 50%;
    margin-bottom: 0.75rem;
    border: 2px solid #d1d5db;
  }

  &__name {
    font-size: 1.125rem;
    font-weight: 600;
    color: #111827;
    margin: 0.25rem 0;
  }

  &__type {
    font-size: 0.875rem;
    color: #6b7280;
  }

  &__tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem;
    justify-content: center;
    margin-bottom: 1rem;
  }

  &__tag {
    background-color: #f3f4f6;
    color: #374151;
    font-size: 0.75rem;
    padding: 0.25rem 0.5rem;
    border-radius: 9999px;
  }

  &__actions {
    display: flex;
    justify-content: center;
    gap: 0.75rem;
  }

  &__button {
    background-color: #2563eb;
    color: #ffffff;
    font-size: 0.875rem;
    padding: 0.5rem 0.875rem;
    border: none;
    border-radius: 0.5rem;
    cursor: pointer;
    transition: background-color 0.2s ease-in-out;

    &:hover {
      background-color: #1d4ed8;
    }

    &:focus {
      outline: 2px solid #93c5fd;
      outline-offset: 2px;
    }
  }
}
</style>