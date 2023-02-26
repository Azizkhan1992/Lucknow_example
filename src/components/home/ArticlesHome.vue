<template>
    <div class="articlesContent">
        <div class="articlesTitle">
            <h3 class="commonP">Articles</h3>
            <div class="goNext backCGrey">
                <img src="../../assets/images/ArrR.png" alt="" class="next">
            </div>
        </div>

        <div class="articlesWrapper">
            <div class="articleItem" v-for="article in articles" :key="article.id">
                <ArtItems :name="article.artItem"/>
                <ArticleTitle :title="article.title" :img="article.img1" :img1="article.img2" :like="article.like"/>
            </div>
        </div>
    </div>
</template>
<script>
import ArtItems from '../commons/ArtItems.vue';
import ArticleTitle from '../commons/ArticleTitle.vue';
export default{
    name: 'home-articles',
    components: {ArtItems, ArticleTitle},
    data(){
        return{
            articles: [
                {
                    id: 1,
                    title: 'How to cook turkey on Natural Gas',
                    artItem: 'cook',
                    like: 28,
                    img1: 'person1',
                    img2: 'person2'
                },
                {
                    id: 2,
                    title: 'Corona virus update: 3,43,287+ cases',
                    artItem: 'corona',
                    like: 28,
                    img1: 'person1',
                    img2: 'person3'
                },
                {
                    id: 3,
                    title: 'Tasty chunk donutes with chocolate',
                    artItem: 'donut',
                    like: 28,
                    img1: 'person1',
                    img2: 'person3'
                },
                {
                    id: 4,
                    title: 'Home made double cheez with popcorn respies',
                    artItem: 'popcorn',
                    like: 28,
                    img1: 'person1',
                    img2: 'person3'
                }
            ]
        }
    }
}
</script>
<style lang="scss">
.articlesContent{
    width: 260px;
    margin-bottom: 12px;

    .articlesWrapper{
        width: 100%;
        margin-top: 16px;
        display: flex;
        flex-direction: column;
        row-gap: 20px;

        .articleItem{
            width: 100%;
            display: flex;
            column-gap: 12px;
        }
    }

    .articlesTitle{
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;

        .goNext{
            width: 50px;
            height: 50px;
            margin-top: -12px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
        }
    }
}

@media screen and (min-width: 1441px) {
    
}
</style>