<template>
    <div class="wraper">
        <div class="backgroundImg" :style="{backgroundImage: `url(${images[lastIndex].img})`}">
            <a class="items" :href="images[currentIndex].href">
                <!-- <img :src="images[lastIndex].img" alt="图片加载失败" class="backgroundImg"> -->
                <img v-for="(item, index) in images" :key="index" :src="item.img" alt="图片加载失败" v-show="currentIndex === index" :class="{myMoveIn: currentIndex === index}">
            </a>
        </div>

        <div class="dots">
            <div v-for="(item, index) in images" :key="index" class="dot" :class="{activeDot: currentIndex === index}" @click="handleClick(index)"></div>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            lastIndex: 0,
            currentIndex: 0,
            images: [
                {
                    href: 'https://www.baidu.com',
                    img: require('../../static/banner4.jpg')
                },
                {
                    href: 'https://www.baidu.com',
                    img: require('../../static/banner2.jpg')
                },
                {
                    href: 'https://www.baidu.com',
                    img: require('../../static/banner3.jpg')
                }
            ]
        }
    },
    created() {

        // setInterval(() => {
        //     this.lastIndex = this.currentIndex
        //     if (this.currentIndex < this.images.length - 1) {
        //         this.currentIndex++
        //     } else {
        //         this.currentIndex = 0
        //     }
        // }, 2000)
    },
    components: {},
    computed: {
    },
    methods: {
        handleClick(index) {
            this.lastIndex = this.currentIndex
            this.currentIndex = index
        }
    }
}
</script>
<style lang='less' scoped>
@keyframes myMoveIn {
    0% {
        left: 350px;
    }
    100% {
        left: 0;
    }
}
@keyframes myMoveOut {
    0% {
        left: 0;
    }
    100% {
        left: -350px;
    }
}

.wraper {
    .backgroundImg {
        width: 750px;
        height: 300px;
        box-sizing: border-box;
        background-size: cover;
    }
    .items {
        img {
            width: 750px;
            height: 300px;
        }
        .myMoveIn {
            animation: myMoveIn 0.5s linear;
            position: relative;
        }
        .myMoveOut {
            animation: myMoveOut 0.5s linear;
            position: relative;
        }
    }
    .dots {
        position: relative;
        top: -60px;
        .dot {
            margin-left: 20px;
            width: 16px;
            height: 16px;
            display: inline-block;
            border-radius: 100%;
            background: #000;
            opacity: 0.2;
        }
        .activeDot {
            background: #fff;
            opacity: 0.8;
        }
    }
}
</style>
