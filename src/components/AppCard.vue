<script>
export default {
    props: {
        thumb: String,
        series: String
    },
    methods: {
        getImagePath(img) {
            return new URL(`${img}`, import.meta.url).href;
        }
    }
}
</script>

<template>
    <div class="card">
        <div class="cover">
            <img :src="getImagePath(thumb)" alt="">
        </div>
        <p>
            {{ series.toUpperCase() }}
        </p>
    </div>
</template>

<style scoped lang="scss">
.card {
    text-align: center;
    img {
        height: 300px;
    }
    padding-top: 20px;

    p {
        font-size: 1.2rem;
        color: white;
    }
}
</style>