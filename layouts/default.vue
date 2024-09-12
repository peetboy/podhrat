<template>
  <div class="w-full">
    <header
      class="flex items-center justify-between p-4 border-b-2 border-black bg-sky-500"
    >
      <h1 class="text-2xl font-bold">Lets Play</h1>
      <Button variant="secondary" size="lg" class="p-4">
        <NuxtLink to="/auth/login">Login</NuxtLink>
      </Button>
    </header>
    <slot></slot>
  </div>
</template>

<script setup lang="ts">
import { Button } from "@/components/ui/button";
</script>
