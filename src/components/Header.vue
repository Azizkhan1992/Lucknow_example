<template>
  <div class="headerContainer" :class="isHeader ? 'mobActive' : 'mobDeactive'">

    <button class="navBtn" @click="isHeader = !isHeader">
      <i class="bi bi-list" v-if="isHeader !== true"></i>
      <i class="bi bi-x-lg" v-else></i>
    </button>

    <div class="navbarContent">

      <div class="navbarLogo">
      <img src="../assets/images/profile.png" alt="" />
      <p class="descP">Alka Yagik</p>
    </div>

    <div class="navbarContainer">
      <div class="navbarWr">
        <div class="navItem" :class="{ active: isRoute == '/' }">
          <div class="iconWr backWh iconH">
            <Icons icon="home" />
          </div>
          <p class="descPCG">
            <router-link class="descPCG" to="/">Home</router-link>
          </p>
        </div>
        <div class="navItem" :class="{ active: isRoute == '/menu' }">
          <div class="iconWr backWh iconH">
            <Icons icon="menu" />
          </div>
          <p class="descPCG">
            <router-link class="descPCG" to="/menu">Menu</router-link>
          </p>
        </div>
        <div class="navItem" :class="{ active: isRoute == '/trend' }">
          <div class="iconWr backWh iconH">
            <Icons icon="fire" />
          </div>
          <p class="descPCG">
            <router-link class="descPCG" to="/trend">Trending</router-link>
          </p>
        </div>
        <div class="navItem" :class="{ active: isRoute == '/settings' }">
          <div class="iconWr backWh iconH">
            <Icons icon="setting" />
          </div>
          <p class="descPCG">
            <router-link class="descPCG" to="/settings">Settings</router-link>
          </p>
        </div>
      </div>
    </div>

    <div class="navbarLogoItem">
      <div class="miniCircle backWh"></div>
      <div class="middleCircle backWh"></div>
      <div class="bigCircle backPurple">
        <div class="circleItem backWh"></div>
      </div>
      <div class="middleBlueCircle backBl"></div>
      <img class="logoImg" src="../assets/images/man.png" alt="" />
      <div class="logoFloat backWh">
        <div class="circleRed backR"></div>
        <p class="descPS">Faster delivery!</p>
        <div class="logoDesc">
          <span class="mainPSB">Know More</span>
          <!-- <img src="../assets/images/ArrR.png" alt="" /> -->
          <Icons icon="rightArr"/>
        </div>
      </div>
    </div>

    </div>


    

    
  </div>
</template>
<script>
import Icons from "./commons/icons.vue";
export default {
  name: "app-header",
  components: { Icons },
  data() {
    return {
      isRoute: this.$route.path,
      isHeader: false
    };
  },
};
</script>
<style lang="scss">
.headerContainer {
  width: 190px;
  height: 794px;
  padding-top: 44px;
  box-sizing: border-box;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  background: transparent !important;

  button.navBtn{
    display: none;
  }

  .navbarContent{
    width: 185px;
    display: flex;
    flex-direction: column;
  }

  .container-fluid{
    flex-direction: column;
    padding: 0 !important;
  }

  .navbarLogoItem {
    width: 100%;
    height: 255px;
    margin-top: 32px;
    position: relative;
    display: flex;
    flex-direction: column;
    justify-content: flex-end;

    .middleBlueCircle {
      width: 60px;
      height: 60px;
      border-radius: 50%;
      position: absolute;
      top: 60px;
      left: 86px;
    }

    .bigCircle {
      width: 76px;
      height: 76px;
      border-radius: 50%;
      position: absolute;
      top: 4px;
      left: 44px;

      .circleItem {
        width: 8px;
        height: 8px;
        border-radius: 50%;
        position: absolute;
        top: 16px;
        left: 20px;
      }
    }

    .middleCircle {
      width: 32px;
      height: 32px;
      border-radius: 50%;
      position: absolute;
      top: 32px;
      left: 24px;
    }

    .miniCircle {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      position: absolute;
      top: 0;
      left: 16px;
    }

    img.logoImg {
      position: absolute;
      top: -32px;
    }

    .logoFloat {
      width: 100%;
      height: 160px;
      border-radius: 25px;
      display: flex;
      flex-direction: column;
      justify-content: flex-end;
      padding: 12px 24px 0 24px;
      box-sizing: border-box;

      .circleRed {
        width: 18px;
        height: 18px;
        border-radius: 50%;
        margin-left: -7px;
        margin-bottom: 16px;
      }

      p.descPB {
        width: 50%;
      }

      .logoDesc {
        width: 100%;
        margin-top: 12px;
        display: flex;
        justify-content: space-between;

        img {
          cursor: pointer;
        }
      }
    }
  }

  .navbarContainer {
    width: 100%;
    margin-top: 55px;

    .navbarWr {
      width: 100%;
      display: flex;
      flex-direction: column;
      row-gap: 40px;

      .navItem {
        width: 100%;
        height: 44px;
        padding-right: 8px;
        box-sizing: border-box;
        display: flex;
        column-gap: 42px;
        align-items: center;
        border-radius: 15px;
        transition: 0.24s linear;
        cursor: pointer;

        &.active {
          background: #ff5454;

          p {
            a.descPCG {
              color: #fff;
            }
          }

          .iconWr {
            background: #df4545;

            .icon {
              svg {
                path {
                  stroke: #fff;
                  fill: #fff;
                }
              }
            }
          }
        }

        p {
          a {
            text-decoration: none;
          }
        }

        .iconWr {
          padding: 8px;
          box-sizing: border-box;
          border-radius: 15px;

          &.iconH {
            .icon {
              padding: 5px 0 0 5px;
              box-sizing: border-box;
            }
          }
        }
      }
    }
  }

  .navbarLogo {
    width: 100%;
    height: fit-content;
    display: flex;
    flex-direction: column;
    align-items: center;
    row-gap: 12px;
  }
}

@media screen and (max-width: 1198px) and (min-width: 768px) {
  .headerContainer{
    transition: width 0.32s linear;
    height: 100%;
    overflow: hidden;
    position: fixed;
    left: 0;
    top: 0;

    &.mobDeactive{
      width: 0;
      padding: 0;
    }

    &.mobActive{
      width: 290px;
      
      background: #eaf1fe !important;
      border-top-right-radius: 15px;
      border-bottom-right-radius: 15px;
      z-index: 299;
    }

    .navbarContent{
      height: 100%;
      width: calc(100% - 64px);
      padding: 16px;
      box-sizing: border-box;

      .navbarLogoItem{
        height: 220px !important;

        .miniCircle{
          top: 2% !important;
          left: 6% !important;
        }

        .middleCircle{
          top: 2% !important;
        }

        .bigCircle{
          top: -5% !important;
        }
        .middleBlueCircle{
          top: 24% !important;
          left: 52% !important;
        }

        img.logoImg{
          width: 100px !important;
          height: 160px !important;
          top: -32px !important;
          left: 64px !important;
          z-index: 0;
        }

        .logoFloat{
          height: 120px;
        }
      }

      .navbarContainer{
        margin-top: 25px !important;
      }
    }

    button.navBtn{
      display: flex;
      width: 36px;
      height: 28px;
      align-items: center;
      justify-content: center;
      background: #fff;
      border-radius: 4px;
      position: fixed;
      top: 12px;
      right: 12px;
      padding-top: 4px;
      box-sizing: border-box;
      border: 0;
      z-index: 299;
    }
  }
}


@media screen and (max-width: 768px) {
  .headerContainer{
    transition: width 0.32s linear;
    height: 100%;
    overflow: hidden;
    position: fixed;
    left: 0;
    top: 0;
    z-index: 299;

    &.mobDeactive{
      width: 0;
      padding: 0;
    }

    &.mobActive{
      width: 290px;
      
      background: #eaf1fe !important;
      border-top-right-radius: 15px;
      border-bottom-right-radius: 15px;
    }

    .navbarContent{
      height: 100%;
      width: calc(100% - 64px);
      padding: 16px;
      box-sizing: border-box;

      .navbarLogoItem{
        height: 220px !important;

        .miniCircle{
          top: 2% !important;
          left: 6% !important;
        }

        .middleCircle{
          top: 2% !important;
        }

        .bigCircle{
          top: -5% !important;
        }
        .middleBlueCircle{
          top: 24% !important;
          left: 52% !important;
        }

        img.logoImg{
          width: 100px !important;
          height: 160px !important;
          top: -28px !important;
          left: 64px !important;
        }

        .logoFloat{
          height: 120px;
        }
      }

      .navbarContainer{
        margin-top: 25px !important;
      }
    }

    button.navBtn{
      display: flex;
      width: 36px;
      height: 28px;
      align-items: center;
      justify-content: center;
      background: #fff;
      border-radius: 4px;
      position: fixed;
      top: 12px;
      right: 12px;
      padding-top: 4px;
      box-sizing: border-box;
      border: 0;
      z-index: 299;
    }
  }
}

</style>
