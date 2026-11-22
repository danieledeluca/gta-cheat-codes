<script setup lang="ts">
import { it } from '@nuxt/ui/locale';

import type { NuxtError } from '#app';

const { error } = defineProps<{
    error: NuxtError;
}>();

useSeoMeta({
    title: error.message,
});
</script>

<template>
    <UApp :locale="it">
        <UError :error="error" />
    </UApp>
</template>
