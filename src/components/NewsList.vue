<template>
    <h2>Articles List</h2>
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
        background-color: #45566d;
        color: white;
        padding: 10px;
        display: block;
        border-bottom: 8px solid #8f6aea;
        margin-bottom: 15px;
        border-radius: 8px 2px 2px 20px;
        overflow-x: hidden;
    }

    
    h2 {
        font-family: Arial, Helvetica, sans-serif;
        font-size: 24px;
        color: white;
    }
</style>