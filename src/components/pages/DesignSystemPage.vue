<template>
  <main class="design-system">
    <h1>Design System</h1>
    <section class="ds-section">
      <h2>buttons</h2>
      <div class="ds-row">
        <BaseButton>Primary</BaseButton>
        <BaseButton variant="secondary">Secondary</BaseButton>
        <BaseButton variant="danger">Danger</BaseButton>
        <BaseButton variant="Disabled">Disabled</BaseButton>
      </div>
    </section>

    <!-- Inputs -->
    <section class="ds-section">
      <h2>inputs</h2>
      <div class="ds-row vertical">
        <BaseInput
        id="input-default"
        label="Artist Name"
        placeholder="Enter Full Name"
        v-model="artistsName"
        />

           <BaseInput
        id="input-desc"
        label="With Desctiption"
        placeholder="e.g Maverick City"
        description="Use full public stage name"
        v-model="artistsName"
        />
           <BaseInput
        id="input-error"
        label="With error"
        placeholder="Enter Full Name"
        v-model="artistsName"
        />
           <BaseInput
        id="input-default"
        label="Artist Name"
        placeholder="Enter Full Name"
        v-model="artistsName"
        />
       
      </div>
    </section>

     <!-- Select -->
    <section class="ds-section">
      <h2>Select</h2>
      <div class="ds-row vertical">
        <BaseSelect
          id="select-role"
          label="Artist Role"
          :options="[
            { label: 'Singer', value: 'singer' },
            { label: 'Producer', value: 'producer' },
            { label: 'Spoken Word', value: 'spoken' }
          ]"
          v-model="selectedRole"
        />

        <BaseSelect
          id="select-role-error"
          label="With Error"
          :options="[
            { label: 'Worship Leader', value: 'worship' },
            { label: 'Speaker', value: 'speaker' }
          ]"
          error="Please select a role"
          v-model="selectedRole"
        />
      </div>
    </section>

    <!-- Avatars -->
    <section class="ds-section">
      <h2>Avatars</h2>
      <div class="ds-row">
        <AvatarAtom src="https://i.pravatar.cc/100?img=3" alt="Micah" :size="48" />
        <AvatarAtom initials="LB" :size="48" />
        <AvatarAtom initials="DJ" :size="64" />
      </div>
    </section>

      <!-- Tags -->
    <section class="ds-section">
      <h2>Tags</h2>
      <div class="ds-row">
        <TagAtom label="Default" />
        <TagAtom label="Success" variant="success" />
        <TagAtom label="Warning" variant="warning" />
        <TagAtom label="Error" variant="error" />
      </div>
    </section>
     
  </main>
</template>

<script setup>
import { ref } from 'vue'

import BaseButton from '@/components/atoms/BaseButton.vue'
import BaseInput from '@/components/atoms/BaseInput.vue'
import AvatarAtom from '@/components/atoms/AvatarAtom.vue';
import BaseSelect from '@/components/atoms/BaseSelect.vue';
import TagAtom  from '@/components/atoms/TagAtom.vue';

const artistsName = ref('')
const selectedRole = ref('')

</script>

<style scoped>
.design-system {
  padding: 2rem;
  background-color: var(--bg-surface);
  color: var(--text-default);
}

.ds-section {
  margin-block-end: 3rem;
}

.ds-row {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}
.ds-row.vertical{
  flex-direction: column;
  align-items: flex-start;
  gap: 1rem;
  max-width: 400px;
}
</style>
