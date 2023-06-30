<template>
    <div>
        <h1> {{ title }}</h1>
        <p><b>Author:</b> {{ author }}</p>
        <p>Description: <br> {{ description }}</p>
        <p>Source: {{ source }} </p>
        <p>Link: <a :href="link">{{ link }}</a></p>
    </div>
</template>

<script>
    export default {
        props: {
            title : String,
            author: String,
            description: String,
            link: String,
            source: String
        } 
    }
</script>

<style scoped>
    p {
        font: 14px normal arial;
    }

    h1 {
        font: 20px normal arial;
    }
</style>