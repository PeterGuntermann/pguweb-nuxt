<template>
  <NuxtPage page-key="static" />
</template>

<script setup>
const title = 'Peter Guntermann';
const description = 'Website von Peter Guntermann';

useHead({
  title: title,
  meta: [{ name: 'viewport', content: 'width=device-width, initial-scale=1' }],
  link: [{ rel: 'icon', href: '/favicon-warnschild-64.ico' }],
  htmlAttrs: {
    lang: 'de',
  },
});
useSeoMeta({
  title: title,
  ogTitle: title,
  ogUrl: 'https://peterguntermann.de',
  ogDescription: description,
  description: description,
  ogType: 'website',
  robots: 'index, follow',
});

const { $bs } = useNuxtApp();

onMounted(() => {
  try {
    const collapse = new $bs.Collapse('#navbarSupportedContent');
    collapse.show();
  } catch (e) {
    console.log('Bootstrap error: ', e);
  }
});
</script>
