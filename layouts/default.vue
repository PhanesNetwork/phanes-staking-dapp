<template class="container">
    <div> <div class="overlay" @click="togglePopup(false)" v-show="showPopup"></div>
    <PopupTokens1 v-show="showPopup"/>

    <!-- Staking Popup -->
    <div class="overlay" @click="toggleStakingPopup(false)" v-show="showStakingPopup"></div>
    <StakingPopup v-show="showStakingPopup"/>

    <!-- Connect wallet Popup -->
    <!-- <div class="overlay" @click="toggleConnectWalletPopup(false)" v-show="showWalletPopup"></div> -->
    <ConnectWalletPopup v-show="showWalletPopup"/>

    <div class="overlay" @click="toggleMintTokenPopup(false)" v-show="showMintTokenPopup"></div>
    <MintTokenPopup v-show="showMintTokenPopup"/>
    <MintTokenSucess v-show="showMintTokenSucess"/>

    <Navbar/>
    <!-- Render pages inside here -->
    <Nuxt />
    <!--  -->
    <FooterCompNew />
    <!-- <FooterComp/> -->
  </div>
   
    
</template>
<script>
import { mapMutations, mapState } from "vuex";
import Navbar from "~/components/layoutComp/Navbar.vue";
import FooterCompNew from "~/components/layoutComp/FooterCompNew.vue"
import FooterComp from "~/components/layoutComp/FooterComp.vue";
import StakingPopup from "~/components/staking/StakingPopup.vue";
import PopupTokens1 from '~/components/popupTokens.vue';
import ConnectWalletPopup from '~/components/connectwallet/ConnectWalletPopup.vue';
import MintTokenPopup from '~/components/mintToken/MintTokenPopup.vue';
import MintTokenSucess from "~/components/mintToken/MintTokenSucess.vue";


  export default {
    computed: {
      ...mapState([
        'showPopup',
        'showStakingPopup',
        'showWalletPopup',
        'showMintTokenPopup',
        'showMintTokenSucess'
      ]),
    },
    methods:{
      ...mapMutations([
          'togglePopup',
          'toggleStakingPopup',
          'toggleConnectWalletPopup',
          'toggleMintTokenPopup',
          'toggleMintTokenSucess'
      ]),
    },
    components:{
    Navbar,
    FooterComp,
    FooterCompNew,
    PopupTokens1,
    StakingPopup,
    MintTokenPopup,
    MintTokenSucess
}
  }
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700;800;900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700;800;900&display=swap');
*,*::after,*::before{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
html{
  font-family: 'Poppins', sans-serif;
  background: #f3f3f3;
  scroll-behavior: smooth;
}

a{
  text-decoration: none;
}
.row{
  width: 100%;
  max-width: 1600px;
  margin-left: 50%;
  transform: translateX(-50%);
  padding: 0 24px;
  @media only screen and (max-width:580px){
    padding: 0 10px;
  }
}
.container{
  position: relative;
}
.overlay{
    background-color: rgba(0, 0, 0, 0.1);
    backdrop-filter: blur(20px);
    width: 100%;
    min-height: 120vh;
    position: fixed;
    top: 0;
    left: 0;
    z-index: 999;
  }
  a{
    text-decoration: none;
  }
</style>
