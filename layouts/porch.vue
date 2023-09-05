<template>
  <div data-layout="porch" class="bg-gray-200 flex items-stretch min-h-screen">
    <div class="flex-1 flex justify-center items-center">
    <!-- <div class="grow flex justify-center items-center"> -->
      <div class="bg-white p-8 rounded shadow">
        <slot />
      </div>
    </div>
    <PorchPoster class="flex-1" />
  </div>
</template>