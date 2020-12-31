<template>
    <header class="header">
        <nav class="nav">
            <NuxtLink to="/">
                <h1>The Blog Title</h1>
            </NuxtLink>
            <h1>
                <NuxtLink :to="infoRoute">{{ isInfoPage ? "close" : "info" }}</NuxtLink>
            </h1>
            <h1>
                <NuxtLink to="/about">About</NuxtLink>
            </h1>
            <h1>
                <NuxtLink to="/galleryPage">Gallery</NuxtLink>
            </h1>
        </nav>
    </header>
</template>

<script>
    export default {
        props: {
                isInfoPage: {
                    type: Boolean,
                    required: false
            }
        }, 
        computed: {
            infoRoute() {
                return this.isInfoPage ? "/" : "/info"
            }
        }
    }
</script>
