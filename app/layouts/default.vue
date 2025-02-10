<template>
  <main>
    <header>
      <UContainer class="flex items-center gap-3 py-2">
        <NuxtLink to="/">
          <div class="flex items-center gap-3">
            <img src="/logo.png" alt="Logo" class="h-8" />
            <p class="font-semibold">Supersaas Lite</p>
          </div>
        </NuxtLink>
        <span class="flex-1" />
        <UButton color="neutral" variant="soft" to="/login">Login</UButton>
        <UButton color="neutral" to="/dashboard">App</UButton>
      </UContainer>
    </header>
    <slot />
  </main>
</template>
