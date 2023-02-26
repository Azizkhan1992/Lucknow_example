<template>
    <div class="sliceItemsContainer">
       <div class="sliceItems backGr" v-for="item in slices" :key="item.id">
            <img :src="require('../../assets/images/' + item.img + '.png')" alt="" class="sliceImg">
            <h5 class="descPSM">{{ item.name }}</h5>
       </div>
    </div>
</template>
<script>
export default {
    name: 'slice-item',
    data() {
        return {
            slices: [
                {
                    id: 1,
                    img: 'all',
                    name: 'All'
                },
                {
                    id: 2,
                    img: 'burger',
                    name: 'Burger'
                },
                {
                    id: 3,
                    img: 'pizza',
                    name: 'Pizza'
                },
                {
                    id: 4,
                    img: 'salad',
                    name: 'Salads'
                },
                {
                    id: 5,
                    img: 'donat',
                    name: 'Donut'
                },
                {
                    id: 6,
                    img: 'drink',
                    name: 'Drinks'
                },
            ],
        }
    },
    mounted(){ 
    },
    methods: {
        
    }
}
</script>

<style lang="scss">
.sliceItemsContainer {
    width: calc(70% - 22px);
    height: 100%;
    display: flex;
    column-gap: 15px;


    .sliceItems{
        width: 100px;
        height: 160px;
        border-radius: 60px;
        padding: 12px 18px;
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: space-evenly;
        transition: 0.12s linear;

        &:hover{
            background: #fff;
            box-shadow: 0px 4px rgba(0, 0, 0, 0.1);

            h5{
                font-size: 1.15rem;
                transition: 0.12s linear;
            }
        }

        &:nth-child(1), &:nth-child(3){
            padding-top: 24px;
        }
        &:nth-child(2){
            padding-bottom: 32px;
        }
        &:nth-child(4){
            padding-bottom: 24px;
        }


        h5{
            text-align: center;
        }
    }
}


</style>