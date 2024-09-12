<template>
  <Card class="w-[600px] shadow-md">
    <CardHeader>
      <CardTitle class="text-2xl text-center">{{ title }}</CardTitle>
    </CardHeader>

    <CardContent>
      <slot></slot>
    </CardContent>

    <CardFooter>
      <div class="flex w-full items-center gap-x-2">
        <Button variant="outline" class="w-full p-6" size="lg">
          <Icon name="logos:google-icon" size="34" />
        </Button>

        <Button variant="outline" class="w-full p-6" size="lg">
          <Icon name="simple-icons:github" size="34" />
        </Button>
      </div>
    </CardFooter>

    <CardFooter>
      <LinkButton :href="linkHref" :label="linkLabel" />
    </CardFooter>
  </Card>
</template>

<script setup lang="ts">
import { defineProps } from "vue";

import {
  Card,
  CardContent,
  CardHeader,
  CardTitle,
  CardFooter,
} from "@/components/ui/card";
import LinkButton from "@/components/custom/LinkButton.vue";

defineProps({
  title: String,
  linkLabel: {
    type: String,
    required: true,
  },
  linkHref: {
    type: String,
    required: true,
  },
});
</script>
