<template>
    <div class="input-wrapper">
        <input :value="value"
         @input="$emit('input',$event.target.value)" 
         @focus="$emit('focus',$event.target.value)" 
         @change="$emit('change',$event.target.value)" 
         @blur="$emit('blur',$event.target.value)"    
         class="g-input" :placeholder="placeholder" :disabled="disabled" type="text"> 
    </div>
</template>

<script>
    export default {
        name :'Input',
        props:{
            disabled:{
                type:Boolean,
                default:false
            },
            placeholder:{
                type:String
            },
            value:{
                type:String
            }
        }
    }
</script>

<style lang="scss" scoped>

    $display:inline-block;
    $input-height:32px;
    $input-border-color:#dcdee2;
    $input-border-radius:4px;
    $input-text-color:#515a6e;
    $input-bg-color:#fff;
    $input-border-color-focus:#57a3f3;
    .input-wrapper{
        display:$display
    }
    .g-input{
        display:$display;
        width: 100%;
        height: $input-height;
        line-height: 1.5;
        padding: 4px 7px;
        font-size: 12px;
        border: 1px solid $input-border-color;
        border-radius: $input-border-radius;
        color: $input-text-color;
        background-color: $input-bg-color;
        transition: border .2s ease-in-out;
        &:hover{
            border: 1px solid $input-border-color-focus; 
        }
        &:focus{
            border: 1px solid $input-border-color-focus; 
        }
        &[disabled]{
            background-color: #f3f3f3;
            opacity: 1;
            cursor: not-allowed; 
            color: #ccc; 
        }
    }
</style>
