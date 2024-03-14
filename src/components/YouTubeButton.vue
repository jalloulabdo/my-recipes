<template>

  <a :href="href" target="_blank" class="btn btn-primary btn-lg">YouTube</a>
</template>

<script setup>
const props = defineProps({
  href: String
})
</script>
