<template>
    <div class="content">
        <img src="../assets/share.jpg" class="bg"/>
        <input type="button" class="click-btn" @click="onClick" v-clipboard:copy="message"/>  
        <div class="mask" v-if="showMask">
            <div class="content-box">
                <div class="mask-content">
                    <img src="../assets/liantonglogo.png" class="logo"/>
                    <div class="tips logo-tips">链接复制成功<br/>请粘贴至浏览器打开或下载APP</div>
                    <img src="../assets/click.png" class="click-img" @click="closeMask">
                </div>
                <img src="../assets/close-icon.png" class="close-btn" @click="closeMask"/>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                showMask: false,
                message: 'https://u.10010.cn/qABsd'
            }
        },
        methods: {
            onClick() {
                this.showMask = true
            },
            closeMask() {
                this.showMask = false
            }
        }
    }
</script>

<style  scoped>

    .content {
        position: relative;
    }
    .bg {
        display: block;
        width: 100%;
        height: 100%;
    }
    .click-btn {
        width: 100%;
        height: 8%;
        position: absolute;
        left: 0;
        bottom: 1.5%;
        z-index: 2;
        background-color: transparent;
        border: none;
        outline:none;
    }
    .mask {
        width: 100%;
        height: 100%;
        position: fixed;
        top: 0;
        left: 0;
        background: rgba(0, 0, 0, 0.6);
    }

    .content-box {
        width: 84%;
        position: fixed;
        top: 50%;
        left: 8%;
        transform: translateY(-50%);
    }
    
    .mask-content {
        width: 100%;
        background: #ffffff;
        border-radius: 6px;
        padding:0 10px 35px;
        box-sizing: border-box;
    }
    .logo {
        display: block;
        width: 57px;
        height: 57px;
        margin: 0 auto;
        padding: 40px 0 0;
    }

    .tips {
        font-size: 20px;
        text-align: center;
        font-weight: bold;
        margin: 15px 0 20px;
    }
           
    .click-img {
        margin: 0 auto;
        width: 90%;
        height: 40px;
        display: block;
        border-radius: 4px;
    }

    .close-btn {
        width: 27px;
        height: 68px;
        margin: 0 auto;
        display: block;
    }

    .text {
        display: none;
    }

</style>