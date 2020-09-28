<template>
  <div class="content">
    <div class="section">
      <img src="../assets/meross-landingPage_01.png" alt="">
    </div>
    <div style="position: relative">
      <div class="sign-section">
        <el-input v-model="info" placeholder="Email address (sign up for exclusive offer)" >
          <el-button slot="append" @click="subscribe">Subscribe</el-button>
        </el-input>
        <div class="protocol">
          <!-- <el-checkbox v-model="checked"></el-checkbox> -->
          * Subscribe to receive news, promotions and recommendations about products and services from Meross, its agencies and partners.
        </div>
      </div>
    </div>
    <div class="section">
       <img src="../assets/meross-landingPage_02.png" alt="">
    </div>
     <div class="section">
       <img src="../assets/meross-landingPage_03.png" alt="">
    </div>
     <div class="section">
       <img src="../assets/meross-landingPage_04.png" alt="">
    </div>
     <div class="section">
       <img src="../assets/meross-landingPage_05.png" alt="">
    </div>
     <div class="section">
       <img src="../assets/meross-landingPage_06.png" alt="">
    </div>
     <div class="section">
       <img src="../assets/meross-landingPage_07.png" alt="">
    </div>
    <div style="position: relative">
      <div class="sign-section sign-section2">
        <el-input v-model="info" placeholder="Email address (sign up for exclusive offer)" >
          <el-button slot="append" @click="subscribe">Subscribe</el-button>
        </el-input>
        <div class="protocol">
          <!-- <el-checkbox v-model="checked"></el-checkbox> -->
          * Subscribe to receive news, promotions and recommendations about products and services from Meross, its agencies and partners.
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
  name: 'Content',
  data() {
    return {
      info: '',
      checked: false,
      tip:  <div>
              <div>1. Voice control, support Alexa, Google Assistant and Siri.</div>
              <div>2. Check garage door status, control it anytime and anywhere.</div>
              <div>3. Get alerts when your garage door is opened, closed, opened for a long time, or it's not closed at bedtime.</div>
              <div>4. PIN code required.</div>
              <div>5. Sound alarm protects your family's safety.</div>
              <div>6. History check - know who and when opens or closes the door from which channel.</div>
              <div>7. Support up to 3 single doors.</div>
            </div>
            
    }
  },
  methods: {
    infoClick() {
      this.$alert(this.tip, {
        confirmButtonText: 'OK',
      })
    },
    subscribe() {
        axios.post('http://xdev.meross.com:38083/landing-page-email',{ email: this.info }).then(({ data }) => {
            this.$alert(data.info, {
              confirmButtonText: 'OK',
            })
        })
      }   

  },
  props: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.content {
  img {
    width: 100%;
    display: block;
  }
  .sign-section {
    text-align: center;
    position: absolute;
    width: 100%;
    top: -1.8rem;
    .el-input-group--append {
      width: 40%;
      margin: 0 auto;
      .el-input__inner{
        border-radius: 1.8rem ;
        height: 3.6rem;
        border: none;
        padding-right: 3rem;
        padding-left: 2rem;
        width: 110%;
        font-size: 0.9rem;
        &::placeholder {
          color: rgb(107, 100, 230)
        }
      }
      .el-input-group__append {
        border-radius: 1rem 3rem 3rem 1rem;
        background-color: rgb(245,120,38);
        border: 0.3rem solid #fff;
        color: #fff;
        font-weight: bold;
        font-size: 1.1rem;
      }
    }
    &.sign-section2 {
      top: -16rem;
    }
    .protocol {
      color: rgb(190, 190, 190);
      width: 38%;
      margin: 0 auto;
      text-align: center;
      font-size: 0.9rem;
      margin-top: 0.5rem;
      // .el-checkbox {
      //   margin-right: 8px;
      //   .el-checkbox__inner {
      //     height: 20px;
      //     width: 20px;
      //     background-color: transparent;
      //     border: 1px solid #ddd;
      //     &::after {
      //       height: 20px;
      //       width: 10px;
      //       border: 4px solid rgb(245,120,38);
      //       border-left: 0;
      //       border-top: 0;
      //       top: -8px;
      //     }
      //   }
      // }
      // .el-button+.el-button {
      //   margin: 0;
      // }
      // .el-button--text {
      //   color: rgb(190, 190, 190);
      //   border-bottom: 1px solid rgb(190, 190, 190);
      //   padding-bottom: 1px;
      // }
    }
    
  }
}

</style>
