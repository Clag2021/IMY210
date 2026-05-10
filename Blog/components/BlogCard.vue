<script setup>

    defineProps({
        post: Object
    })

</script>

<template>

    <div class="blog-card">
        <NuxtLink :to="`/posts/${post.slug}`">
            <h2 class="title">{{ post.title }}</h2>
        </NuxtLink>

        <p>{{ post.author }} | {{ new Date(post.publishedAt).toLocaleDateString('en-CA') }} | {{ post.category }}</p>
        <p><b>About:</b> {{ post.brief }}</p>
    </div>

</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&family=Stack+Sans+Notch:wght@200..700&family=Uncial+Antiqua&display=swap');

.blog-card {

    border: 5px solid #9667E0;
    border-radius: 10px;
    padding: 10px 20px;
    font-family: Roboto, sans-serif;
    margin: 10px 10px;
    background-color: #F2EBFB;

}

.title {
    font-family: 'Stack Sans Notch', sans-serif;

}

</style>
