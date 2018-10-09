<template>
<div class="g-button-group">
    <slot></slot>
</div>
</template>

<script>
    
</script>

<style lang="scss">
.g-button-group {
    display: inline-flex;
    vertical-align: middle;

    .g-button {
        margin-left: -1px;
        border-radius: 0;
        &:first-child {
            border-radius: var(--border-radius) 0 0 var(--border-radius);
        }
        &:last-child {
            border-radius: 0 var(--border-radius) var(--border-radius) 0;
        }
        &:hover {
            position: relative;
            z-index: 1;
        }
    }
}
</style>
