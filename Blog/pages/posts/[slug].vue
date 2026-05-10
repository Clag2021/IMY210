<script setup>
    const route = useRoute()
    const slug = route.params.slug

    const config = useRuntimeConfig()

    const { data } = await useFetch(`${config.public.apiUrl}/api/blogs`)

    const post = computed(() => data.value.data?.[0])

</script>

<template>
    <Navbar />

    <div class="container">
    <div v-if="post" class="blog-post">

        <h1>{{ post.title }}</h1>
        <p class="details"><b>By</b> {{ post.author }} <b>on</b> {{ new Date(post.publishedAt).toLocaleDateString('en-CA')  }} <b>at</b> {{ new Date(post.publishedAt).toLocaleTimeString() }}</p>
        <p class="tag">{{ post.category }}</p>
        <div >{{ post.content }} </div>

        </div>

        <div class="image"> 
            <img :src="`http://localhost:1337${post.coverImage.url}`" :alt="post.coverImage.alternativeText" />

        </div>
    </div>

    



</template>

<style scoped>

.blog-post {
    padding: 0 50px;
    font-family: Roboto;
    width: 700px;
}

img {
    margin: 20px auto;
    width: 500px;
}

.container {
    margin: 0 auto;
    display: flex;
    margin-top: 30px;
    margin-left: 30px;
    margin-right: 30px;
    background-color: #F2EBFB;
}


.tag {
    border-radius: 10px;
    background-color: #d4bbfc;
    padding: 5px;
    width: 60px;
    font-weight: bold;
}

.details {
    font-size: 1.1em;
}


h1 {
    font-family: 'Stack Sans Notch', sans-serif;
}

</style>
