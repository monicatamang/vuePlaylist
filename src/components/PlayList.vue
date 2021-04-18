<template>
    <div>
        <p>{{ title }}</p>
        <h4>{{ artist }}</h4>
    </div>
</template>

<script>
    export default {
        name: "play-list",
        props: {
            title: String,
            artist: String
        },
    }
</script>

<style scoped>

</style>