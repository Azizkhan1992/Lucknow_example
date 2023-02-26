<template>
    <div class="TitleContainer">
        <span class="miniP title">{{ title }}</span>
        
        <div class="titleItemsWr">
            <img :src="require('../../assets/images/icons/' + img+'.svg')" alt="" class="artImg1">
        <img :src="require('../../assets/images/icons/' + img1+'.svg')" alt="" class="artImg2">

        <div class="numLikesWrapper">
            <img src="../../assets/images/icons/like.svg" alt="" class="likeImg">

            <span class="miniRM">{{ like }}+</span>
        </div>
        </div>
    </div>
</template>
<script>
export default{
    name: 'app-title',
    props:{
        title: {
            type: String,
            default: ''
        },
        like: {
            type: [String, Number],
            default: 0
        },
        img: {
            type: String,
            default: ''
        },
        img1: {
            type: String,
            default: ''
        }
    }
}
</script>
<style lang="scss">
.TitleContainer{
    width: 180px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    row-gap: 3px;

    span.title{
        line-height: 135%;
    }

    .titleItemsWr{
        width: 100%;
        display: flex;


        img{
        width: 24px;
        height: 24px;
        border-radius: 50%;
        border: 1px solid #fff;

        &.artImg2{
            margin-left: -8px;
        }
    }

    .numLikesWrapper{
        width: 55px;
        height: 24px;
        display: flex;
        align-items: center;
        background: #fff8d5;
        border-radius: 15px;
        border: 1px solid #fff;
        justify-content: center;
        column-gap: 8px;
        margin-left: -6px;

        img.likeImg{
            width: 14px;
            height: 14px;
            border: 0;
        }
    }
    }
}
</style>