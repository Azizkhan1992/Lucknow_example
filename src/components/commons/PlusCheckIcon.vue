<template>
    <div class="plusCheck backBlack"
    :class="iconName !== 'plus' ? 'checked' : ''"
    >
    <Icons v-if="iconName === 'plus'" icon="plus"/>
    <Icons v-else icon="check"/>
    </div>
</template>
<script>
import Icons from './icons.vue';
export default{
    name: 'app-plus',
    components: {Icons},
    props: {
        iconName: {
            type: String,
            default: 'plus'
        }
    }
}
</script>
<style lang="scss">
.plusCheck{
    width: 32px;
    height: 32px;
    border-radius: 50%;
    display: flex;
    align-items: center;
    justify-content: center;
    cursor: pointer;
    transition: 0.24s linear;

    &:hover{
        background: #fff;
        border: 2px solid #000000;

        svg{
            rect{
                fill: #000000 !important;
                stroke: #000000 !important;
            }
        }
    }

    &.checked{
        background: #fff;
        border: 2px solid #000000;

        &:hover{
            background: #000000;
            border: 0;

            svg{
                path{
                    fill: #fff;
                    stroke: #fff;
                }
            }
        }

        svg{
            path{
                fill: #000000;
                stroke: #000000;
                transition: 0.24s linear;
            }
        }
    }

    .icon{
        padding: 10px 0 0 12px;
        box-sizing: border-box;

        svg{

            rect{
                fill: #fff;
                stroke: #fff;
                transition: 0.24s linear;
            }
        }
    }

}
</style>