<template>
    <button @click="$emit('click')" class="g-button"  :class="{[`g-button-${type} icon-${iconPosition}`]: true}" >
        <g-icon v-if="icon && !loading" :name="icon"></g-icon>
        <g-icon v-if="loading" class="loading icon" name="loading" ></g-icon>
        <div class="content"> 
            <slot></slot> 
        </div>  
    </button>
</template>

<script>
export default {
    props: {
        icon: {},
        type: {
            type: String,
            default: 'parimary',
            validator(value) {
                return ['parimary', 'success', 'error'].indexOf(value) != -1
            }
        },
        disabled: {
            type: Boolean,
            default: false
        },
        loading: {
            type: Boolean,
            default: false
        },
        iconPosition: {
            type: String,
            default: 'left',
            validator(value) {
                return value === 'left' || value === 'right'
            }
        }
    }
}
</script>

<style lang="scss">

@keyframes spin {
    0% {
        transform: rotate(0deg)
    }

    100% {
        transform: rotate(360deg)
    }
}

.g-button {
    height: var(--button-height);
    padding: 0 1em;
    border-radius: var(--border-radius);
    border: 1px solid var(--border-color);
    background: var(--button-bg);
    display: inline-flex;
    justify-content: center;
    align-items: center;
    vertical-align: middle;
    color: #fff;

    &:active {
        background-color: var(--button-active-bg);
    }

    &:focus {
        outline: none;
    }

    >.content {
        order: 2;
    }

    >.icon {
        order: 1;
        margin-right: .1em;
    }

    >.loading {
        animation: spin 1s infinite linear;
    }

    &.icon-right {
        >.content {
            order: 1;
        }

        >.icon {
            order: 2;
            margin-right: 0;
            margin-left: .1em;
        }
    }
}

.g-button-parimary {
    background-color: #2d8cf0;
    border-color: #2d8cf0;

    &:active {
        background-color: #2d8cf0;
        opacity: .9;
    }
}

.g-button-success {
    background-color: #47cb89;
    border-color: #47cb89;

    &:active {
        background-color: #47cb89;
        opacity: .8;
    }
}

.g-button-error {
    background-color: #ed4014;
    border-color: #ed4014;

    &:active {
        background-color: #ed4014;
        opacity: .8;
    }
}
</style>
