<template>
  <ClientOnly>
    <CardWrapper
      title="Register"
      link-href="/auth/login"
      link-label="Already have an account?"
    >
      <form @submit.prevent="onSubmit" class="space-y-6">
        <div class="space-y-4">
          <FormField v-slot="{ componentField }" name="name">
            <FormItem>
              <FormLabel>Name</FormLabel>
              <FormControl>
                <Input type="text" placeholder="Name" v-bind="componentField" />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>

          <FormField v-slot="{ componentField }" name="email">
            <FormItem>
              <FormLabel>Email</FormLabel>
              <FormControl>
                <Input
                  type="email"
                  placeholder="Email"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>

          <FormField v-slot="{ componentField }" name="password">
            <FormItem>
              <FormLabel>Password</FormLabel>
              <FormControl>
                <Input
                  type="password"
                  placeholder="Password"
                  v-bind="componentField"
                />
              </FormControl>
              <FormMessage />
            </FormItem>
          </FormField>

          <Button type="submit" class="w-full" size="lg">Register</Button>
        </div>
      </form>
    </CardWrapper>
  </ClientOnly>
</template>

<script lang="ts" setup>
import CardWrapper from "@/components/auth/CardWrapper.vue";
import LinkButton from "@/components/custom/LinkButton.vue";
import {
  FormControl,
  FormField,
  FormItem,
  FormLabel,
  FormMessage,
} from "@/components/ui/form";
import { Input } from "@/components/ui/input";
import { useForm } from "vee-validate";
import { RegisterSchema } from "@/schemas";
import { toTypedSchema } from "@vee-validate/zod";

const formSchema = toTypedSchema(RegisterSchema);
const form = useForm({ validationSchema: formSchema });

const onSubmit = form.handleSubmit((values) => {
  console.log("Form submitted!", values);
});
</script>
