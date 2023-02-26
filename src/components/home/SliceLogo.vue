<template>
    <div class="sliceLogoContainer backPurple">
        <div class="fireCircle backFire">
            <img src="../../assets/images/fire.png" alt="" class="fire">
        </div>
        <img src="../../assets/images/orange.png" alt="" class="orange">
        <img src="../../assets/images/bitten-apple.png" alt="" class="apple">
        <img src="../../assets/images/cheese.png" alt="" class="cheese">
        <img src="../../assets/images/burger.png" alt="" class="burger">
        <Icons icon="burger" class="burger" size="320" key="burger" />
        <h3 class="commonPSB">
            -50% Off
        </h3>
        <p class="descPSSB">the full price of burgers</p>
    </div>
</template>
<script>
import Icons from '../commons/icons.vue';
export default{
    name: 'slice-logo',
    components: {Icons},
}
</script>
<style lang="scss">
.sliceLogoContainer{
    width: 260px;
    height: 160px;
    border-radius: 30px;
    padding: 30px 20px;
    box-sizing: border-box;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;
    position: relative;

    &::after{
        content: "";
        width: 100%;
        height: 100%;
        position: absolute;
        top: 0;
        left: 0;
        background: #fff;
        opacity: 0.3;
        border-radius: 30px;
        z-index: 0;
    }

    .orange{
        width: 42px;
        height: 42px;
        position: absolute;
        top: 15px;
        left: 108px;
        z-index: 1;
    }

    .apple{
        width: 72px;
        height: 72px;
        position: absolute;
        top: -42px;
        left: 20px;
        z-index: 1;
    }

    .cheese{
        width: 38px;
        height: 32px;
        position: absolute;
        right: -16px;
        bottom: 68px;
        z-index: 1;
    }

    .icon{

        &.burger{
        transform: rotateZ(-32deg) scale(1) !important;
        position: absolute;
        top: -240px !important;
        right: -58px !important;
        z-index: 1;
    }
    }

    img.burger{
        display: none;
    }

    .fireCircle{
        width: 24px;
        height: 24px;
        padding: 8px 0;
        box-sizing: border-box;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        border-radius: 50%;
        position: absolute;
        top: -48px;
        right: 128px;
        z-index: 1;
    }
}

@media screen and (max-width: 1198px) and (min-width: 768px) {
    .sliceLogoContainer{

        img.burger{
            display: block;
            position: absolute;
            top: -64px;
            right: 0;
            transform: scale(1.5) rotateZ(-30deg);
        }

        .icon{
            &.burger{
                display: none;
            }
        }
    }
}


@media screen and (min-width: 1441px) {
    .sliceLogoContainer{
        // width: 420px !important;

        .icon{

            &.burger{
            transform: rotateZ(-30deg) scale(1) !important;
            right: -60px !important;
            top: -160% !important;
        }
        }

        .apple{
            width: 120px !important;
            height: 120px !important;
            left: -6px;
            top: -64px !important;
        }

        .fireCircle{
            width: 42px !important;
            height: 42px !important;
            right: 50% !important;
        }

        h3.commonPB{
            font-size: 3rem !important;
        }
        p.descP{
            font-size: 1.15rem !important;
        }
    }
}

@media screen and (max-width: 768px) {
    .sliceLogoContainer{

        .icon{
            &.burger{
                display: none;
            }
        }

        img.burger{
            display: block;
            transform: rotateZ(-30deg) scale(1.25);
            position: absolute;
            top: -48px;
            right: 0;
        }
    }
}
</style>