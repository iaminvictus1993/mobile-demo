<template>
    <div class="menu">
        <div class="tab" v-for="(item,index) in tabs" :key="index" @click="handleClick(item.txt)">
            <img :src="item.img" alt="加载图片失败">
            <span class="txt">{{item.txt}}</span>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            tabs: [
                {
                    img: require('../../../static/singer.png'),
                    txt: '歌手'
                },
                {
                    img: require('../../../static/rank.png'),
                    txt: '排行'
                },
                {
                    img: require('../../../static/radio.png'),
                    txt: '电台'
                }
            ]
        }
    },
    created() {},
    components: {},
    computed: {},
    methods: {
        handleClick(data) {
            window.alert(data)
        }
    }
}
</script>
<style lang='less' scoped>
.menu {
    height: 140px;
    padding: 0px 75px;
    .tab {
        width: 200px;
        display: inline-block;
        img {
            width: 60px;
            height: 60px;
        }
        .txt {
            position: relative;
            top: -16px;
        }
    }
}
</style>
