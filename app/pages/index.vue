<script setup lang="ts">
import sanAndreasCheatCodes from '~/assets/cheat-codes/san-andreas.json';

const router = useRouter();
const route = useRoute();

const filter = ref(route.query.q?.toString() || '');

const cheatCodes = computed(() => {
    return sanAndreasCheatCodes.filter((cheat) => {
        // eslint-disable-next-line style/max-len
        return `${cheat.category} - ${cheat.effect} - ${cheat.description}`.toLowerCase().includes(filter.value.toLowerCase());
    });
});
</script>

<template>
    <div class="overflow-hidden rounded-md">
        <NuxtImg src="/covers/san-andreas.jpg" class="w-full" />
    </div>
    <UForm class="my-4 sm:my-6 lg:my-8">
        <UFieldGroup class="w-full">
            <UInput
                v-model="filter"
                placeholder="Cerca un trucco"
                icon="i-lucide-search"
                class="w-full"
                @update:modelValue="router.push({ query: { q: filter || undefined } })"
            />
            <UButton type="submit" label="Cerca" />
        </UFieldGroup>
    </UForm>
    <div v-if="cheatCodes.length > 0" class="grid gap-8">
        <div
            v-for="(cheats, category) in Object.groupBy(cheatCodes, (cheat) => cheat.category)"
            :key="category"
        >
            <div class="mb-4 text-2xl">
                {{ category }}
            </div>
            <div class="*:first:rounded-t-md *:last:rounded-b-md">
                <div v-for="(cheat, index) in cheats" :key="index" class="group flex flex-wrap items-center overflow-hidden border-x border-t border-default last:border-b hover:bg-muted">
                    <div class="flex-1 p-3 font-semibold">
                        {{ cheat.effect }}
                    </div>
                    <div class="flex flex-3 flex-wrap items-center gap-2 border-l border-default p-3 group-hover:border-accented max-md:basis-full max-md:border-t">
                        <NuxtImg
                            v-for="(code, codeIndex) in cheat.codes.split(', ')"
                            :key="codeIndex"
                            :src="`/controller-icons/${code.toLowerCase()}.svg`"
                            class="size-8"
                        />
                    </div>
                    <div class="basis-full border-t border-default p-3 text-sm text-muted group-hover:border-accented">
                        {{ cheat.description }}
                    </div>
                </div>
            </div>
        </div>
    </div>
    <UAlert
        v-else
        color="warning"
        title="Nessun trucco trovato"
        icon="i-lucide-triangle-alert"
    />
</template>
