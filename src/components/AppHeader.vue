<script>
export default {
    data() {
        return {
            menu: [
                {
                title: "CHARACTERS",
                },
                {
                title: "COMICS",
                },
                {
                title: "MOVIES",
                },
                {
                title: "TV",
                },
                {
                title: "GAMES",
                },
                {
                title: "COLLECTIBLES",
                },
                {
                title: "VIDEOS",
                },
                {
                title: "FANS",
                },
                {
                title: "NEWS",
                },
                {
                title: "SHOP",
                },
            ],
        };
    },
}
</script>

<template>
<header>
    <div class="header-img">
        <img src="../assets/img/dc-logo.png" alt="Logo DC">
    </div>
    <ul class="header-nav">
        <li v-for="item in menu">
            <a href="">{{ item.title }}</a>
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
                a:hover {
                    color: $blue;
                }
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