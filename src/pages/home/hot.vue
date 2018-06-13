<template>
    <div>
        <div class="title">热门推荐</div>
        <List></List>
    </div>
</template>

<script>
import List from '@/components/list'
export default {
    data() {
        return {}
    },
    created() {},
    components: {List},
    computed: {},
    methods: {}
}
</script>
<style lang='less' scoped>
.title {
    font-size: 40px;
    bold: 20;
    margin-bottom: 20px;
}
</style>
