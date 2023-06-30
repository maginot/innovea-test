<template>
    <div>
        <h1> {{ title }}</h1>
        <p><b>Author:</b> {{ author }}</p>
        <p><b>Description:</b> <br> {{ description }}</p>
        <p><b>Source:</b> {{ source }} </p>
        <p><b>Link:</b> <a :href="link">{{ link }}</a></p>
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
        font-size: 14px;
        font-family: Arial, Helvetica, sans-serif;
    }

    p a {
        color: #cfcfcf;
    }

    h1 {
        font-size: 20px;
        font-family: Arial, Helvetica, sans-serif;
    }
</style>