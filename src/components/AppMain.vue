<script>
import AppCard from './AppCard.vue';
import ProductCard from './AppCard.vue';

export default {
    data() {
        return {
            comics: [
                { title: "Characters" },
                { title: "Comics" },
                { title: "Movies" },
                { title: "Tv" },
                { title: "Games" },
                { title: "Videos" },
                { title: "News" },
            ],

            buyitems: [
                { title: "DIGITAL COMICS", image: "buy-comics-digital-comics.png" },
                { title: "MERCHANDISE", image: "buy-comics-merchandise.png" },
                { title: "SHOP LOCATOR", image: "buy-comics-shop-locator.png" },
                { title: "SUBSCRIPTION", image: "buy-comics-subscriptions.png" },
                { title: "DC POWER VISA", image: "buy-dc-power-visa.svg" },
            ],
            
            shop: [
                { title: "Shop Dc" },
                { title: "Shop Dc Collectibles" },
            ],

            dc: [
                { title: "Term Of Use" },
                { title: "Privacy policy(New)" },
                { title: "Ad Choices" },
                { title: "Advertising" },
                { title: "Jobs" },
                { title: "Subscriptions" },
                { title: "Talent WorkShops" },
                { title: "CPSC Certificates" },
                { title: "Ratings" },
                { title: "Shop Help" },
                { title: "Contact Us" },
            ],
            
            sites: [
                { title: "DC" },
                { title: "MAD Magazines" },
                { title: "DC Kids" },
                { title: "DC Universe" },
                { title: "DC Power Visa" },
            ],

            products: [
                { thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg", price: "$19.99", series: "Action Comics", type: "comic book" },
                { thumb: "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg", price: "$3.99", series: "American Vampire 1976", type: "comic book" },
                { thumb: "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg", price: "$16.99", series: "Aquaman", type: "graphic novel" },
                { thumb: "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg", price: "$2.99", series: "Batgirl", type: "comic book" },
                { thumb: "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg", price: "$3.99", series: "Batman", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg", price: "$2.99", series: "Batman Beyond", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg", price: "$3.99", series: "Batman/Superman", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg", price: "$4.99", series: "Batman/Superman Annual", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg", price: "$5.99", series: "Batman: The Joker War Zone", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg", price: "$6.99", series: "Batman: Three Jokers", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg", price: "$4.99", series: "Batman: White Knight Presents: Harley Quinn", type: "comic book" },
                { thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg", price: "$16.99", series: "Catwoman", type: "graphic novel" },
            ]
        };
    },
    methods: {
        getImagePath (imageName) {
            return new URL(`../assets/img/${imageName}`, import.meta.url).href;
        },
    },
    components: {
        AppCard,
    },
}
</script>

<template>
    <section>
        <div class="upper-main">
            <div class="row">
                <div class="col" v-for="element in products">
                    <AppCard :thumb="element.thumb" :series="element.series"/>
                </div>
            </div>
        </div>
        
        <div class="icon-main">
            <div class="buyitem" v-for="item in buyitems" :key="item.title">
                <div class="buyitem-content">
                    <img :src="getImagePath(item.image)" alt="">
                    <a :href="item.link" class="buyitem-title">{{ item.title }}</a>
                </div>
            </div>
        </div>
    
        <div class="lower-main">
            <div>
                <h3>DC COMICS</h3>
                <ul>
                    <li v-for="item in comics">
                        <a href="">{{ item.title }}</a>
                    </li>
                </ul>
                
                <h3>SHOP</h3>
                <ul>
                    <li v-for="item in shop">
                        <a href="">{{ item.title }}</a>
                    </li>
                </ul>
            </div>
            
            <div>
                <h3>DC</h3>
                <li v-for="item in dc">
                    <a href="">{{ item.title }}</a>
                </li>
            </div>

            <div>
                <h3>SITES</h3>
                <ul>
                    <li v-for="item in sites">
                        <a href="">{{ item.title }}</a>
                    </li>
                </ul>
            </div>
        </div>

    </section>
</template>

<style lang="scss" scoped>
@use "../style/partials/_variables" as *;
@use "../style/partials/_mixin" as *;
   
section {
    width: 100%;
    .upper-main {
        @include flex(row,start,center);
        background-color: $black;
        font-size: 2rem;
    }
    
    .row {
        display: flex;
        justify-content: space-between;
        flex-wrap: wrap;
        .col {
            width: 15%;
            margin-bottom: 2em;
        }
    }

    .icon-main {
        @include flex(row,start,center);
        padding-left: 200px;
        height: 15vh;
        background-color: $blue;

        .buyitem {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-right: 20px;

            .buyitem-content {
                @include flex(row, start, center);
                margin-bottom: 10px;
            }

            .buyitem-image {
                width: 50px;
                height: auto;
            }

            .buyitem-title {
                color: white;
                text-align: center;
            }
        }
    }
        
    .lower-main {
        @include flex(row,start,start);
        font-family: sans-serif;
        font-size: 1.1rem;
        padding-left: 200px;
        padding-top: 10px;
        gap: 30px;
        background-image: url(../assets/img/footer-bg.jpg);
        background-size: cover;
        height: 40vh;
        color: $white;
        
        h3 {
            margin: 20px 0;
        };
        
        li {
            margin: 7px 0;
            font-size: 0.8rem; 
        };
        
        a {
            color: $grey;
            &:hover {
                text-decoration: underline;
                color: $white;
            }
        };
    }
}
</style>
