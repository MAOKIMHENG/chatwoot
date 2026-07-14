<script setup>
defineProps({
  disableBranding: {
    type: Boolean,
    default: false,
  },
});
</script>

<template>
  <div
    v-if="!disableBranding"
    class="px-0 py-3 flex justify-center"
  >
    <p class="m-0 text-center text-xs leading-4 text-n-slate-11">
      {{ $t('AI_DISCLAIMER') }}
    </p>
  </div>
  <div v-else class="p-3" />
</template>
