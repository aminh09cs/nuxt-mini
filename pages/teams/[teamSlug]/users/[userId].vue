<script lang="ts" setup>
const route = useRoute();
const message = computed(() => `${route.params.teamSlug} + ${route.params.userId }`
)
</script>

<template>
    <div>
       {{message}}
    </div>
</template>

<style scoped>

</style>
