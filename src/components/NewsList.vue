<template>
    <p>News List</p>
    <template v-for="item in articles" :key="item.author">
        <news-list-item :author="item.author" :title="item.title" :description="item.description" :link="item.url" :source="item.source.name" class="news-list-item" />
    </template>
</template>

<script>
    import NewsListItem from './NewsListItem.vue';

    export default {
        data() {
            return {
                articles: []
            }
        },
        components: { NewsListItem },
        created() {
            var url = 'https://newsapi.org/v2/everything?' +
                      'q=Apple&' +
                      'from=2023-06-25&' +
                      'sortBy=popularity&' +
                      'apiKey=d685a5b91c36462facf937689aedcaaf';

            var req = new Request(url);
            fetch(req)
                .then((response) => { 
                    return response.json().then((data) => {
                        console.log(data);
                        this.articles = data.articles;
                        // JSON.stringify(data, null, 2);
                    }).catch((err) => {
                        console.log(err);
                    }) 
                });
        }
    }
</script>

<style scoped>
    .news-list-item {
        background-color: #ccc;
        padding: 10px;
        display: block;
        width: 100%;
        border-bottom: 2px solid #777;
        margin-bottom: 10px;
    }

</style>