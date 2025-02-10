<template>
  <div class="flex-1">
    <header
      class="flex h-14 min-w-0 items-center justify-between gap-3 border-b border-zinc-200 p-4 dark:border-white/10"
    >
      <UButton
        icon="i-lucide-menu"
        variant="ghost"
        color="neutral"
        class="md:hidden"
        @click="toggleMobileMenu"
      />
      <p class="truncate text-sm">{{ title }}</p>
      <span class="flex-1" />
      <slot name="actions" />
    </header>
    <slot />
  </div>
</template>

<script setup lang="ts">
defineProps<{
  title: string
}>()

const isMobileOpen = useState('mobile-sidebar')

function toggleMobileMenu() {
  isMobileOpen.value = !isMobileOpen.value
}
</script>
