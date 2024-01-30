<template>
    <main>
        <CustomHeader></CustomHeader>
        <slot />
    </main>
</template>

<script setup>
import { description, title } from '~/state';

    useHead({
        script: [
            {
                src: 'https://pro.fontawesome.com/releases/v5.10.0/js/all.js',
                body: true
            }
        ],
        htmlAttrs:{
            lang: 'es'
        },

    })
    useSeoMeta({
        title: title,
        ogTitle: title,
        description: description,
        ogDescription: description,
        ogImage: 'https://luisjdev.com/favicon.ico'
    })
</script>

<style>
main {
    display: flex;
    width: 100vw;
    min-height: 100vh;
    max-width: 1366px;
    flex-direction: row;
    background-attachment: fixed;
}

main > * {
    flex: 1;
}

@media screen and (max-width: 1000px) {
    main {
        flex-direction: column;
    }
}
</style>