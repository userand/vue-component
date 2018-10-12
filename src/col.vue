<template>
    <div class="g-col" :class="`g-col-${span} g-offset-${offset}`"></div>
</template>

<script>
export default {
    props:{
        span:{
            type:[Number,String]
        },
        offset:{
            type:[Number,String]
        },
       
    },
    mounted() {
        
    }
}
</script>

<style scoped lang="scss">

.g-col{
    height: 100px;
    width: 50%;
    border:1px solid red;

    $class-prefix: g-col-;
    $offset-prefix: g-offset-;

    @for $n from 1 through 24 {
      &.#{$class-prefix}#{$n} {
        width: ($n / 24) * 100%;
      }
    }

    @for $n from 1 through 24 {
      &.#{$offset-prefix}#{$n} {
        margin-left: ($n / 24) * 100%;
      }
    }
}
</style>


