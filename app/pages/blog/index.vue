<script lang="ts" setup>
const route = useRoute()
const blog = await queryCollection('content').path(route.path).first()
const articles = await queryCollection('content')
  .where('id', 'NOT LIKE', 'content/blog/index.md')
  .all()

useSeoMeta({
  title: blog?.title,
  description: blog?.description,
})
</script>
<template>
  <div class="mx-auto max-w-3xl space-y-8 py-24">
    <ContentRenderer class="prose" v-if="blog" :value="blog" />

    <main class="space-y-8">
      <UCard v-for="(article, articleKey) in articles">
        <div class="text-pretty text-[var(--ui-text-muted)]">
          {{ article.meta.date }}
        </div>
        <h1 class="mt-4 text-2xl font-bold">{{ article.title }}</h1>

        <template #footer>
          <NuxtLink class="text-[var(--ui-primary)]" :to="article.path"
            >Read more</NuxtLink
          >
        </template>
      </UCard>
    </main>
  </div>
</template>
