<template>
    <div class="wraple">
        <div class="item" v-for="(item, index) in contents" :key="index">
            <div class="upPart">
                <img :src="item.img" alt="图片加载失败">
                <div class="playNum">
                    <i class="listen"></i>
                    <span>{{item.playNum}}</span>
                </div>
                <div class="playButton"></div>
            </div>
            <span>{{item.txt}}</span>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            contents: [
                {
                    img: require('../../static/zjl.jpeg'),
                    txt: '催泪大杀器！万人黄河大合唱',
                    playNum: '930.5万'
                },
                {
                    img: require('../../static/hot2.jpeg'),
                    txt: '催泪大杀器！万人黄河大合唱',
                    playNum: '930.5万'
                },
                {
                    img: require('../../static/hot3.jpeg'),
                    txt: '催泪大杀器！万人黄河大合唱',
                    playNum: '930.5万'
                },
                {
                    img: require('../../static/hot4.jpeg'),
                    txt: '催泪大杀器！万人黄河大合唱',
                    playNum: '930.5万'
                },
                {
                    img: require('../../static/hot5.jpeg'),
                    txt: '催泪大杀器！万人黄河大合唱',
                    playNum: '930.5万'
                },
                {
                    img: require('../../static/hot6.jpg'),
                    txt: '催泪大杀器！万人黄河大合唱',
                    playNum: '930.5万'
                }
            ]
        }
    },
    created() {},
    components: {},
    computed: {},
    methods: {}
}
</script>
<style lang='less' scoped>
.wraple {
    width: 750px;
    height: 750px;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    overflow: hidden;
    .item {
        width: 240px;
        height: 320px;
        .upPart {
            position: relative;
            .playButton {
                width: 48px;
                height: 48px;
                background-image: url(../../static/list_sprite.png);
                background-size: cover;
                position: absolute;
                right: 0;
                top: 180px;
            }
            .playNum {
                position: absolute;
                left: 5px;
                top: 200px;
                color: #fff;
                font-size: 14px;
                .listen {
                    display: inline-block;
                    width: 20px;
                    height: 20px;
                    background-image: url(../../static/music.png);
                    background-repeat: no-repeat;
                    background-size: cover;
                }
            }
            img {
                width: 250px;
                height: 250px;
            }
        }
    }
}
</style>
