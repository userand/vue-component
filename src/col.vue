<template>
<div class="g-col" :class="colClass" :style="colStyle">
    <slot> </slot>
</div>
</template>

<script>
export default {
    data() {
        return {
            gutter: 0
        }
    },
    computed: {
        colStyle() {
            let gutter = this.gutter
            return {
                paddingLeft: gutter / 2 + 'px',
                paddingRight: gutter / 2 + 'px'
            }
        },
        colClass() {
            let {
                span,
                offset,
                xs,
                sm,
                md,
                lg,
                xl,
                xxl
            } = this
            return [
                `g-col-${span}`,
                offset && `g-offset-${offset}`,
                xs && `g-col-xs-${xs}`,
                sm && `g-col-sm-${sm}`,
                md && `g-col-md-${md}`,
                lg && `g-col-lg-${lg}`,
                xl && `g-col-xl-${xl}`,
                xxl && `g-col-xxl-${xxl}`
            ]
        }
    },
    props: {
        span: {
            type: [Number, String]
        },
        offset: {
            type: [Number, String]
        },
        xs: {
            type: [Number, String]
        },
        sm: {
            type: [Number, String]
        },
        md: {
            type: [Number, String]
        },
        lg: {
            type: [Number, String]
        },
        xl: {
            type: [Number, String]
        },
        xxl: {
            type: [Number, String]
        }
    },
    mounted() {

    }
}
</script>

<style lang="scss" scoped>
.g-col {
    height: 50px;

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

    @media (max-width: 577px) {
        $class-prefix: g-col-xs-;
        $offset-prefix: g-offset-xs-;

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

    @media (min-width: 578px) and (max-width: 768px) {
        $class-prefix: g-col-sm-;
        $offset-prefix: g-offset-sm-;

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

    @media (min-width: 769px) and (max-width: 993px) {
        $class-prefix: g-col-md-;
        $offset-prefix: g-offset-md-;

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

    @media (min-width: 994px) and (max-width: 1201px) {
        $class-prefix: g-lg-xs-;
        $offset-prefix: g-offset-xs;

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

    @media (min-width: 1202px) and (max-width: 1601px) {
        $class-prefix: g-col-xl-;
        $offset-prefix: g-offset-xl-;

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

    @media (min-width: 1601px) {
        $class-prefix: g-col-xxl-;
        $offset-prefix: g-offset-xxl-;

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

}
</style>
