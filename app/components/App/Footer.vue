<template>
    <UFooter
        class="border-t border-t-accented"
        :ui="{ container: 'max-lg:py-4', center: 'max-lg:mt-0', left: 'max-lg:mt-0' }"
    >
        <div class="text-center text-sm text-muted">
            &copy; {{ new Date().getFullYear() }} - Daniele De Luca
        </div>
    </UFooter>
</template>
