<template>
  <Button variant="link" size="lg" as-child class="font-normal w-full">
    <NuxtLink :to="href">{{ label }}</NuxtLink>
  </Button>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";
import { Button } from "@/components/ui/button";

defineProps({
  href: {
    type: String,
    required: true,
  },
  label: {
    type: String,
    required: true,
  },
});
</script>

<style></style>
