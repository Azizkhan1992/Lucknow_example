<template>
    <div class="homeContainer backWh">
        <div class="homeTitle">
            <div class="titleLeft">
                <div class="titleLogo">
                <h1 class="commonT">Welcome To Lucknow</h1>
                <img src="../assets/images/smile.png" alt="">
            </div>

            <div class="itemSearch backGr">
                <img src="../assets/images/search.png" alt="">
            </div>
            </div>

            <div class="itemCart backDGr">
                <Icons icon="cart"/>
            </div>
        </div>

        <HomeSlices/>

        <div class="mobileContent mt-80">
            <SliceLogo/>
        </div>

        <div class="HomeContent">
            <AllContent/>
            <ArticlesHome/>
        </div>

        <div class="planshContent mt-96">
            <SliceLogo/>
            <ArticlesHome/>
        </div>

        <div class="mobileArticles mt-42">
            <ArticlesHome/>
        </div>

    </div>
</template>
<script>
import Icons from '@/components/commons/icons.vue';
import HomeSlices from '@/components/home/homeSlices.vue';
import AllContent from '@/components/home/AllContent.vue';
import ArticlesHome from '@/components/home/ArticlesHome.vue';
import SliceLogo from '@/components/home/SliceLogo.vue';
export default{
    name: 'app-home',
    components: {Icons, HomeSlices, AllContent, ArticlesHome, SliceLogo},
    
}
</script>

<style lang="scss">
.homeContainer{
    width: 1120px;
    height: 794px;
    border-radius: 35px;
    padding: 45px 67px 25px 53px;
    box-sizing: border-box;

    .planshContent{
        display: none;
    }

    .mobileContent{
        display: none;
    }

    .mobileArticles{
        display: none;
    }


    .HomeContent{
        width: 100%;
        margin-top: 45px;
        display: flex;
        justify-content: space-between;
    }

    .homeTitle{
        width: 100%;
        display: flex;
        justify-content: space-between;
        position: relative;

        .titleLeft{
            width: calc(70% - 24px);
            display: flex;
            justify-content: space-between;


            .itemSearch{
            width: 50px;
            height: 50px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 15px;
            cursor: pointer;
        }

        .titleLogo{
            width: calc(50% - 18px);
            display: flex;
            align-items: center;
            position: relative;

            img{
                position: absolute;
                right: 24px;
                bottom: 7px;
            }
        }
        }

        .itemCart{
            width: 50px;
            height: 50px;
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            padding-top: 4px;
            padding-left: 4px;
            box-sizing: border-box;
            cursor: pointer;
            position: absolute;
            right: 0;
            z-index: 9;

            &::after{
                content: "";
                width: 12px;
                height: 12px;
                background: #ff5454;
                border-radius: 50%;
                position: absolute;
                top: -2px;
                right: -2px;
            }
        }

        
    }
}

@media screen and(min-width: 1441px) {
    .homeContainer{
        width: 1240px !important;
        height: fit-content !important;


        .HomeContent{

            .allItemsContainer{

                .ItemsWr{
                    .items{

                        &.b-center{
                            left: 36% !important;
                        }

                        &.item-b, &.b-center{
                            bottom: -24px !important;
                        }
                        
                        &.item-r, &.center, &.item-l{
                            height: 340px !important;

                            .itemFloat{
                                height: 265px !important;
                                row-gap: 12px;
                            }
                        }
                    }
                }
            }

            .articlesContent{


                .articlesWrapper{
                    .articleItem{

                        .artItemContent{
                            width: 80px !important;
                            height: 80px !important;
                        }
                    }
                }
            }
        }
    }
}


@media screen and (max-width: 1439px) and (min-width: 1198px) {
    .homeContainer{
        width: 880px !important;
        padding: 25px 25px 10px 30px !important;

        .homeTitle{

            .titleLeft{
                .titleLogo{
                    width: calc(65% - 12px) !important;
                }
            }
        }
    }
}

@media screen and (max-width: 1198px) and (min-width: 769px) {
    .homeContainer{
        width: 720px !important;
        margin: 0 auto;
        height: fit-content !important;
        padding: 25px 25px 10px 30px !important;

        .planshContent{
            width: 100%;
            display: flex !important;
            flex-direction: row-reverse;
            align-items: flex-start;
            justify-content: space-between;

            .sliceLogoContainer{
                margin-top: 48px;
            }
        }

        .HomeContent{

            .articlesContent{
                display: none;
            }

            .allItemsContainer{
                width: 100% !important;
            }
        }

        .homeTitle{

            .titleLeft{

                .titleLogo{
                    width: calc(75% - 12px) !important;
                }
            }
        }
    }
}

@media screen and (max-width: 768px) {
    .homeContainer{
        width: 320px !important;
        height: fit-content !important;
        margin: 0 auto;
        padding: 15px 15px 8px 20px !important;

        .mobileArticles{
            display: block !important;
        }

        .mobileContent{
            display: block !important;
        }

        .HomeContent{

            .allItemsContainer{
                width: 100% !important;

                .ItemsWr{
                    height: 780px;
                    align-items: center;
                    justify-content: center !important;
                    row-gap: 24px !important;

                    .items{

                        &.item-b, &.b-center{
                            display: none !important;
                        }
                    }
                }
            }

            .articlesContent{
                display: none !important;
            }
        }

        .sliceContainer{
            height: 520px;

            .sliceItemsContainer{
                width: 100% !important;
                flex-wrap: wrap;
                justify-content: space-between;
            }

            .homeSliceLogo{
                display: none !important;
            }
        }

        .homeTitle{

            .titleLeft{
                width: calc(80% - 24px) !important;

                .itemSearch{
                    display: none !important;
                }

                .titleLogo{
                    width: 100% !important;

                    img{
                        width: 42px !important;
                        height: 46px !important;
                        right: 20px !important;
                        bottom: 12px !important;
                    }
                }
            }
        }
    }
}
</style>