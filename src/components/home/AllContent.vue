<template>
  <div class="allItemsContainer">
    <div class="ItemsHeader">
      <h3 class="commonP">All Items</h3>
      <img src="../../assets/images/filter.png" alt="" />
    </div>

    <div class="ItemsWr">
      <div
        class="items"
        v-for="item in items"
        :key="item.id"
        :class="
          item.id == 1
            ? 'item-l'
            : '' || item.id == 2
            ? 'center'
            : '' || item.id == 3
            ? 'item-r'
            : '' || item.id == 4
            ? 'item-b'
            : '' || item.id == 5
            ? 'b-center'
            : '' || item.id == 6
            ? 'item-b'
            : ''
        "
      >
        <LikeIcons v-if="item.id == 1" like-name="fire" />
        <LikeIcons v-if="item.id == 2" like-name="like" />
        <LikeIcons v-if="item.id == 6" like-name="star" />
        <img
          :src="require('../../assets/images/' + item.img1 + '.png')"
          alt=""
          class="img1"
        />
        <div class="itemFloat backWBSh">
          <p class="mainP">{{ item.name }}</p>
          <span class="miniPCG">{{ item.title }}</span>
          <div class="priceWr">
            <p class="descPB">${{ item.price }}</p>
            <PlusCheck v-if="item.id == 2" icon-name="check" />
            <PlusCheck v-else />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import PlusCheck from "../commons/PlusCheckIcon.vue";
import LikeIcons from "../commons/LikeIcons.vue";
export default {
  name: "all-items",
  components: { PlusCheck, LikeIcons },
  data() {
    return {
      items: [
        {
          id: 1,
          name: "Burger Wanted",
          title:
            "Rels, Zoodies, Garnein Sesasam Dessigns, Redeshchein, Avocade",
          price: 29,
          img1: "img1",
          isLike: true,
        },
        {
          id: 2,
          name: "Butter Chciken",
          title: "Reis, Sous-vide Chicken, Penaut Satay, Babyspian",
          price: 56,
          img1: "img3",
          isLike: false,
        },
        {
          id: 3,
          name: "Hi, Salmon",
          title: "Rels, Zoodies, Garnein Dressings, Avacode Edanmame, Maris.",
          price: 69,
          img1: "img5",
        },
        {
          id: 4,
          img1: "img01",
        },
        {
          id: 5,
          img1: "img02",
        },
        {
          id: 6,
          img1: "img03",
        },
      ],
    };
  },
};
</script>
<style lang="scss">
.allItemsContainer {
  width: calc(70% - 24px);
  position: relative;
  // overflow: hidden;

  .ItemsWr {
    width: 100%;
    height: 240px;
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
    margin-top: 5px;

    .items {
      width: 205px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      position: relative;

      &.item-b {
        position: absolute;
        height: 38px;
        box-shadow: -2px 4px 8px 2px rgba(0, 0, 0, 0.1);
        border-top-left-radius: 30px;
        border-top-right-radius: 30px;
        z-index: 99;

        img {
          top: -55px !important;
          left: 15% !important;
        }

        .itemFloat {
          display: none;
        }

        &:nth-child(4) {
          bottom: -18px;
          left: 0;
        }

        &:nth-child(6) {
          right: 0;
          bottom: -18px;

          .likeContainer {
            top: -36px;
          }
        }
      }
      &.b-center {
        width: 205px;
        height: 55px;
        position: absolute;
        left: 35%;
        bottom: -18px;
        box-shadow: -2px 4px 8px 2px rgba(0, 0, 0, 0.1);
        border-top-left-radius: 30px;
        border-top-right-radius: 30px;

        img {
          overflow: overlay;
          top: -58px !important;
          left: 20% !important;
        }

        .itemFloat {
          display: none;
        }
      }

      .likeContainer {
        position: absolute;
        right: 0;
        top: 14px;
        z-index: 49;
      }

      img.img1 {
        position: absolute;
        top: -8px;
        left: calc(10% - 12px);
      }

      .itemFloat {
        width: 100%;
        border-radius: 30px;
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        padding: 0 12px 8px 24px;
        box-sizing: border-box;

        span{
          margin-top: 7px;
        }

        p.mainP {
          font-weight: 800;
        }

        .priceWr {
          width: 100%;
          display: flex;
          justify-content: space-between;
          align-items: center;
        }
      }

      &.item-l {
        height: 240px;

        // img.img1{
        //   width: 178px;
        //   height: 134px;
        // }

        .itemFloat {
          height: 165px;
          margin-bottom: -12px;
        }
      }
      &.item-r {
        height: 270px;
        margin-top: -20px;

        // img.img1{
        //   width: 175px;
        //   height: 145px;
        // }

        .itemFloat {
          height: 170px;
        }
      }

      &.center {
        width: 210px;
        height: 232px;
        margin-bottom: 12px;

        img.img1 {
          // width: 136px;
          // height: 125px;
          left: calc(20% - 12px);
        }

        .itemFloat {
          height: 150px;
          background: #f2eeee;
        }
      }
    }
  }

  .ItemsHeader {
    display: flex;
    align-items: center;
    column-gap: 30px;
  }
}

@media screen and (min-width: 1441px) {
  
}

@media screen and (max-width: 1439px) and (min-width: 1100px) {
  .allItemsContainer{
    .ItemsWr{

      .items{
        width: 170px !important;

        img.img1{
          width: 180px !important;
          height: 130px !important;
          top: 12px !important;
          left: calc(10% - 16px) !important;
        }

        &.center{
          width: 180px !important;
        }

        &.item-b{
          bottom: -38px !important;

          img.img1{
            top: -48px !important;
          }
        }
        &.b-center{
          bottom: -38px !important;

          img.img1{
            top: -48px !important;
            left: 8px !important;
          }
        }
      }
    }
  }
}

@media screen and (max-width: 1199px) and (min-width: 768px) {
  .allItemsContainer{

    .ItemsWr{

      .items{

        &.item-l, &.item-r{
          width: 195px !important;
        }
        &.center{
          width: 205px !important;
        }

        &.item-b, &.b-center{
          display: none;
        }
      }
    }
  }
}
</style>
