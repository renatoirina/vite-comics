<script>
export default {
    data() {
        return {
            menu: [
                { title: "CHARACTERS", hovered: false },
                { title: "COMICS", hovered: false },
                { title: "MOVIES", hovered: false },
                { title: "TV", hovered: false },
                { title: "GAMES", hovered: false },
                { title: "COLLECTIBLES", hovered: false },
                { title: "VIDEOS", hovered: false },
                { title: "FANS", hovered: false },
                { title: "NEWS", hovered: false },
                { title: "SHOP", hovered: false },
            ],
        };
    },
    methods: {
        changeColor(item) {
            item.hovered = true;
        },
        resetColor() {
            this.menu.forEach(item => item.hovered = false);
        }
    }
}
</script>

<template>
    <header>
        <div class="header-img">
            <img src="../assets/img/dc-logo.png" alt="Logo DC">
        </div>
        <ul class="header-nav">
            <li v-for="item in menu" :key="item.title">
                <a href="#" 
                   @mouseover="changeColor(item)" 
                   @mouseout="resetColor"
                   :style="{ color: item.hovered ? $blue : 'black' }">
                    {{ item.title }}
                </a>
            </li>
        </ul>
    </header>
    <div class="jumbotron-container">
        <img src="../assets/img/jumbotron.jpg" alt="Jumbotron Image" class="jumbotron-image">
    </div>
</template>

<style lang="scss" scoped>
@use "../style/partials/_variables" as *;
@use "../style/partials/_mixin" as *;

header {
    @include flex(row, space-between, center);
    padding: 10px;
    height: 152px;

    a {
        text-decoration: none;
    }


    .header-img {
        @include flex(row, center, center); 
        flex-grow: 1;

        img {
            width: 17%;
            margin-left: 100px;
        }
    }

    .header-nav {
        @include flex(row, end, center);
        gap: 20px;
        width: 60%;
        margin-right: 300px;

        li {
            padding: 66px 0;
            font-family: sans-serif;
            font-size: 0.8rem;
            font-weight: 700;
            border-bottom: 5px solid transparent;

            &:hover {
                border-bottom: 5px solid $blue;
                color: $blue;
            }
        }
    }
}

.jumbotron-container {
    width: 100%;
    position: relative;
    overflow: hidden;
    height: 400px;

    .jumbotron-image {
        width: 100%;
        height: auto;
        position: relative;
    }
}
</style>
