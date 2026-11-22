<template>
    <UHeader title="GTA cheat codes" :toggle="false">
        <template #right>
            <UColorModeButton />

            <UTooltip text="Open on GitHub">
                <UButton
                    color="neutral"
                    variant="ghost"
                    to="https://github.com/danieledeluca/gta-cheat-codes"
                    target="_blank"
                    icon="i-simple-icons-github"
                />
            </UTooltip>
        </template>
    </UHeader>
</template>
