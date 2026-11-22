<script setup lang="ts">
import { it } from '@nuxt/ui/locale';

useSeoMeta({
    titleTemplate: (titleChunk) => {
        return titleChunk
            ? `${titleChunk} | GTA cheat codes`
            : 'GTA cheat codes';
    },
    description: 'lorem ipsum',
});
</script>

<template>
    <UApp :locale="it">
        <NuxtLayout>
            <NuxtPage />
        </NuxtLayout>
    </UApp>
</template>
