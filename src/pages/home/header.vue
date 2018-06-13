<template>
    <header class="header" :class="{topOffSet: isShowCancel}">
        <div class="title">music app</div>
        <div class="search">
            <i class="icon"></i>
            <input v-model="search" :class="{smallWidth: isShowCancel}" @focus="handleFocus" />
            <div class="cancel" v-show="isShowCancel" @click="$emit('update:isShowCancel', false)">取消</div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            search: '搜索'
        }
    },
    created() {},
    components: {},
    computed: {},
    props: {
        isShowCancel: {
            type: Boolean,
            required: true
        }
    },
    methods: {
        handleFocus() {
            this.search === '搜索' && (this.search = '')
            this.$emit('update:isShowCancel', true)
        }
    }
}
</script>
<style lang='less' scoped>
.header {
    position: relative;
    top: 0px;
    transition: all 0.3s linear;
    .title {
        background-color: #31c27c;
        height: 60px;
        line-height: 60px;
        color: white;
        font-size: 40px;
        display: block;
    }
    .search {
        background-color: #31c27c;
        height: 100px;
        line-height: 100px;
        color: white;
        position: relative;
        .icon {
            background: url(../../../static/search1.png) no-repeat;
            color: #fff;
            background-size: cover;
            width: 50px;
            height: 50px;
            position: absolute;
            z-index: 2;
            top: 25px;
            left: 50px;
        }
        input {
            position: absolute;
            top: 25px;
            left: 50px;
            box-sizing: border-box;
            width: 650px;
            background-color: #55a772;
            border: none;
            height: 50px;
            color: #fff;
            font-size: 28px;
            padding-left: 50px;
            &:focus {
                outline: none;
            }
        }
        .smallWidth {
            width: 600px;
        }
    }
    .cancel {
        display: inline-block;
        position: absolute;
        font-size: 28px;
        right: 20px;
    }
}
.topOffSet {
    top: -60px;
}
</style>
