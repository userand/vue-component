<template>
    <button class="button">
         <slot></slot>
    </button>
</template>

<script>
    export default{



    }

</script>

<style lang="scss">
    .button{
        padding: 0 1em;
        background: pink;

      &:hover{
          background: red;
      }  
    }
</style>
