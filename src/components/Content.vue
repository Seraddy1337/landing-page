<template>
  <div class="content">
    <div class="section-1">
    </div>
    <div class="sign-section">
      <el-input v-model="info" placeholder="Email address (sign up for exclusive offer)">
        <el-button slot="append" @click="subscribe">subscribe</el-button>
      </el-input>
      <div class="protocol">
        <!-- <el-checkbox v-model="checked"></el-checkbox> -->
        * Your personal data will not be shared with any third-party companies. For more details, please check the Meross <el-button type="text" @click="infoClick">privacy policy</el-button>
      </div>
    </div>
    <div class="section-2">
      <img src="https://d2utgrzbxqaq8t.cloudfront.net/public/staticfile/1559195061618/9794107.jpg" alt="">
    </div>
    <div class="section-3">
      <img src="https://d2utgrzbxqaq8t.cloudfront.net/public/staticfile/1559195061618/9794107.jpg" alt="">
    </div>
    <div class="section-4">
      <img src="https://d2utgrzbxqaq8t.cloudfront.net/public/staticfile/1559195061618/9794107.jpg" alt="">
    </div>
    <div class="sign-section">
      <el-input v-model="info" placeholder="Email address (Email address (sign up for exclusive offer))">
        <el-button slot="append" @click="subscribe">Subscribe</el-button>
      </el-input>
      <div class="protocol">
        <el-checkbox v-model="checked"></el-checkbox>I agress to the <el-button type="text" @click="infoClick">Term of Use</el-button> and have read and understood the <el-button type="text" @click="infoClick">Privacy Policy</el-button>
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
      tip: '福利绝对是v老师极乐世界分开了就啊开始减肥就啊帅哭了经典福克斯将就啊睡懒觉分开了睡大觉阿克琉斯分就看了撒娇分了快点睡觉觉拉萨附近了快就离开就记录'
    }
  },
  methods: {
    infoClick() {
      this.$alert(this.tip, {
        confirmButtonText: 'OK',
      })
    },
    subscribe() {
      // if(this.checked) {
        axios.post('http://xdev.meross.com:38083/landing-page-email',{ email: this.info }).then(({ data }) => {
          // if(data.code === 200) {
            this.$alert(data.info, {
              confirmButtonText: 'OK',
            }) 
          // }
          // this.$alert('提交成功', {
          //   confirmButtonText: '确定',
          // }) 
        })
      }   
      // else {
      //   this.$alert('请阅读并同意', {
      //     confirmButtonText: '确定',
      //   })  
      // }
      
    // }
  },
  props: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss">
.content {
  background-color: blue;
  .section-1 {
    height: 12rem;
    background: url('https://d2utgrzbxqaq8t.cloudfront.net/public/staticfile/1559195061618/9794107.jpg') no-repeat;
    background-size: 100%;
  }
  .sign-section {
    text-align: center;
    .el-input-group--append {
      width: 600px;
      margin: 0 auto;
      .el-input__inner{
        border-radius: 28px ;
        height: 56px;
        border: none;
        padding-right: 50px;
        padding-left: 20px;
        width: 110%;
        font-size: 14px;
        &::placeholder {
          color: rgb(107, 100, 230)
        }
      }
      .el-input-group__append {
        border-radius: 15px 50px 50px 15px;
        background-color: rgb(245,120,38);
        border: 5px solid #fff;
        color: #fff;
        font-weight: bold;
        font-size: 18px;
      }
    }
    .protocol {
      color: rgb(190, 190, 190);
      .el-checkbox {
        margin-right: 8px;
        .el-checkbox__inner {
          height: 20px;
          width: 20px;
          background-color: transparent;
          border: 1px solid #ddd;
          &::after {
            height: 20px;
            width: 10px;
            border: 4px solid rgb(245,120,38);
            border-left: 0;
            border-top: 0;
            top: -8px;
          }
        }
      }
      .el-button+.el-button {
        margin: 0;
      }
      .el-button--text {
        color: rgb(190, 190, 190);
        border-bottom: 1px solid rgb(190, 190, 190);
        padding-bottom: 1px;
      }
    }
    
  }
}

</style>
