<script setup>
const route = useRoute();

const { data } = await useFetch(
    `http://www.omdbapi.com/?apikey=69302644&i=${route.params.id}`,
    {
        pick: ["Plot", "Title", "Error"],
        key: `/movies/${route.params.id}`
    }
)
if (data.value.Error === "Incorrect IMDb ID.") {
    showError({ statusCode: 404, statusMessage: "Page Not Found" })
}
useHead({
    title: data.value.Title,
    meta: [
        {name: "description", content: data.value.Plot},
        {name: "twitter:card", content: `summary_large_image`},
    ]
})
</script>

<template>
    <div>
        {{ data }}
    </div>
</template>

<style scoped>

</style>
