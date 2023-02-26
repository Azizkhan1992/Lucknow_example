<template>
    <div class="sliceContainer">
        <SliceItems/>

        <div class="homeSliceLogo">
            <SliceLogo/>
        </div>
    </div>
</template>
<script>
import SliceItems from './sliceItems.vue';
import SliceLogo from './SliceLogo.vue';
export default{
    name: 'home-slice',
    components: {SliceItems, SliceLogo}
}
</script>
<style lang="scss">
.sliceContainer{
    width: 100%;
    height: 160px;
    margin-top: 28px;
    display: flex;
    justify-content: space-between;
}

@media screen and (max-width: 1198px) and (min-width: 768px) {
    .sliceContainer{

        .sliceItemsContainer{
            width: 100% !important;
        }

        .homeSliceLogo{
        display: none;
    }
    }
}

@media screen and (min-width: 1441px) {
    .sliceContainer{

        .homeSliceLogo{
            // height: 100%;
            // width: 480px;
        }

        .sliceItemsContainer{
        justify-content: space-between;

        .sliceItems{
            // height: 260px;
            // width: 200px;
            // border-radius: 120px;

            h5.descPSM{
                font-size: 1.5rem;
            }
        }
    }
    }
}
</style>