<template>
<div class="g-row" :style="rowStyle" >
    <slot> </slot>
</div>
</template>

<script>
export default {
    props: {
        gutter: {
            type: [Number, String]
        }
    },
    computed: {
        rowStyle() {
            let gutter = this.gutter
            return {
                marginLeft: -gutter / 2 + 'px',
                marginRight: -gutter / 2 + 'px'
            }
        }
    },
    mounted() {
        this.$children.forEach(item => {
            item.gutter = this.gutter
        })
    }
}
</script>

<style lang="scss" scoped>
    .g-row {
        display: flex;
        flex-wrap: wrap;
    }
</style>
