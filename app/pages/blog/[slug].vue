<script lang="ts" setup>
const route = useRoute()
const blog = await queryCollection('content').path(route.path).first()
</script>
<template>
  <div class="prose mx-auto max-w-3xl py-24">
    <NuxtLink to="/blog">
      <UButton
        color="primary"
        variant="ghost"
        size="sm"
        icon="i-heroicons-chevron-left"
        class="pl-0"
        >Back</UButton
      >
    </NuxtLink>

    <ContentRenderer class="mt-8" v-if="blog" :value="blog" />
  </div>
</template>
