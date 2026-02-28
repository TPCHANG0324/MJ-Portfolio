<template>
    <div class="headerBar">
      <div class="marquee">
         <div class="marquee__inner" ref="marquee">
            <span class="portfolioText">
            ⟡ 2026 ⟡ PORTFOLIO ⟡ 2026 ⟡ PORTFOLIO&nbsp;
            </span>
            <span class="portfolioText">
            ⟡ 2026 ⟡ PORTFOLIO ⟡ 2026 ⟡ PORTFOLIO&nbsp;
            </span>
            <span class="portfolioText">
            ⟡ 2026 ⟡ PORTFOLIO ⟡ 2026 ⟡ PORTFOLIO&nbsp;
            </span>
            <span class="portfolioText">
            ⟡ 2026 ⟡ PORTFOLIO ⟡ 2026 ⟡ PORTFOLIO&nbsp;
            </span>
         </div>
      </div>
    </div>
    <div class="centerBG">
      <img ref="art" class="artLayout" src="../assets/image/art-layout.svg">
      <img class="hanji" src="../assets/image/hanji.svg">
      <img ref="illu" class="illustration" src="../assets/image/illustration.svg">
    </div>
    <div class="wrapper">
       <div class="mainBlock">
          <div class="mainBar">
            <div class="iconHome">
               <img src="../assets/image/icon-home.svg">
            </div>
            <img class="iconGroup" src="../assets/image/icon-group.svg"> 
          </div>
          <div class="mainCenter">
            <span class="containText">Graphic Design</span>
            <img class="iconPen" src="../assets/image/icon-pen.svg">
          </div>
          <div class="mainLogo">
            <img class="iconLogo" src="../assets/image/icon-logo.svg">
            <img class="iconCursor" src="../assets/image/icon-cursor.svg">
          </div>
          <div class="author">MEI&nbsp-&nbsp;JIN HUANG</div>
       </div>
    </div>
</template>

<script setup>
import { onMounted, ref } from "vue"
import { gsap } from "gsap"

const marquee = ref(null)
const art = ref(null)
const illu = ref(null)

onMounted(() => {
  const width = marquee.value.offsetWidth / 8

  gsap.to(marquee.value, {
    x: -width,
    duration: 10,
    ease: "none",
    repeat: -1
  })

  gsap.to(art.value, {
   scale: 1.05,
   y: -8,
   duration: 3.2,
   repeat: -1,
   yoyo: true,
   ease: "sine.inOut"
   })
  gsap.to(illu.value, {
    scale: 1.08,
    duration: 2.6,
    repeat: -1,
    yoyo: true,
    ease: "power1.inOut"
  })
})
</script>

<style scoped lang="scss">
   .headerBar {
      background-color: #FC8031;
      height: 53px;
      overflow: hidden;
      display: flex;
      align-items: center;

      .marquee {
         width: 100%;
         overflow: hidden;
         }

      .marquee__inner {
         display: flex;
         width: max-content;
      }
      .portfolioText {
         color: #FBF5E9;
         font-style: italic;
         font-size: 26.5px;
         display: block;
         width: 100%;
         height: 53px;
         white-space: nowrap;
         line-height: 53px;
         text-align: center;
         font-family: "Avenir";
      }
   }
   .centerBG {
      position: relative;

      .hanji {
         position: fixed;
         top: 27%;
         left: 50%;
         transform: translate(-50%, -50%);
         display: block;
         height: auto;
         width: 334px;
         z-index: 10;
      }

      .artLayout {
         position: fixed;
         top: 13%;
         left: 26%;
         width: 220px;
      }

      .illustration {
         position: fixed;
         top: 22%;
         right: 27%;
         width: 220px;
      }
   }
   .wrapper {
      background-color: #28201B;
      border-radius: 48px;
      position: fixed;
      top: 87%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 11;
      display: block;
      height: 100%;
      width: 60%;
      padding: 50px;

      .mainBlock {
         background-color: #443F3B;
         border-radius: 24px;
         height: 100%;
         width: 100%;
         box-shadow: inset 0 0 10px rgba(255, 255, 255, 0.2);
         padding: 32px 48px;
      }

      .mainBar {
         height: 40px;
         .iconHome {
            float: left;
            border-right: 1px solid #FC8031;
            width: 70px;
         }
         .iconGroup {
            float: right;
         }
      }

      .mainCenter {
         position: relative;
         padding: 50px 36px 0 36px;
         width: 100%;

         .containText {
            font-size: 18px;
            color: #FC8031;
            font-family: "Avenir";
            font-weight: 400;
         }
         .iconPen {
            position: absolute;
            width: 250px;
            top: 40%;
            left: 50%;
            transform: translate(-50%, -50%);
         }
      }

      .mainLogo {
         padding: 24px 36px 0px 36px;
         width: 100%;
         position: relative;

         .iconLogo {
            display: block;
            object-fit: contain;
            margin: 0 auto;
            width: 100%;
         }
         .iconCursor {
            position: absolute;
            bottom: -20%;
            right: 3%;
            transform: translate(0%, 50%);
            width: 30px;
         }
      }

      .author {
         margin-top: 48px;
         text-align: center;
         font-size: 18px;
         color: #FC8031;
         font-family: "Avenir";
         font-weight: bold;
      }
   }
</style>
