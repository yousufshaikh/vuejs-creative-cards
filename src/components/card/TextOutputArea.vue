<template>
  <div>
      <p :style="styleObj">{{displayText}}</p>
  </div>
</template>

<script>
    export default{
        props: {
            displayText: [String],
            containerHeight : {
                type: Number,
                default: 200
            }
        },
        computed:{
            styleObj: function(){
                return{
                    height: this.containerHeight + 'px'
                }
            }
        }
    }
</script>

<style scoped>
p{
    font-family: 'Times New Roman', Times, serif;
    font-size: 42px;
    line-height: 42px;
    text-shadow: 2px 2px 2px #aaa;
    color: #4d4d4d; 
    margin: 5px 0;
    border: 1px dotted gray;
    white-space: pre-line;
    overflow: hidden;
    }
</style>

