<script lang="ts" setup>
  definePageMeta({
    layout: "porch",
  });
</script>

<template>
  <div class="w-96">
    <DvStack>
      <h1 class="text-2xl">Please login</h1>
      <DvInput placeholder="Username" />
      <DvInput placeholder="Password" />
      <DvButton>Login</DvButton>
      <div>Forgot password</div>
    </DvStack>
  </div>
</template>