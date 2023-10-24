<template lang="pug">
v-app
    v-col.text-center
        div(style="border-bottom: 2px solid white;")
            h1 {{ title  }}
</template>

<script lang="ts">
export default {
    name: 'AboutPage',
    data() {
        return {
            title: '商品一覧',
        };
    },
};
</script>