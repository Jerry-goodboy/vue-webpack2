<template id="dialog-template">
  <div class="dialogs">
    <div class="dialog" :class="{ 'dialog-active': show }">
      <div class="dialog-content">
        <div class="close rotate closeX">
          <i class="el-icon-close" @click="closeDialog"></i>
        </div>
        <slot name="header"></slot>
        <slot name="body"></slot>
        <slot name="footer"></slot>
      </div>
    </div>
    <div class="dialog-overlay"></div>
  </div>
</template>
<script>
  export default {
    props:['show'],
    methods:{
      closeDialog(){
        this.$emit("closeDialogX");
      }
    }
  }
</script>
<style scoped>
  .dialogs{
    padding: 0 10px;
  }
  .dialog-content{
    position: relative;
  }
  .closeX{
    position: absolute;
    top: 20px;
    right: 20px;
    cursor: pointer;
    color: #fff;
    font-size: 16px;
  }
  .closeX > i{
    display: block;
  }
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    font-family: Ubuntu, simHei, "Microsoft YaHei", sans-serif;
  }

  html {
    font-size: 12px;
    font-weight: 400
  }

  body {
    font-size: 1rem
  }

  table,
  td,
  th {
    border-collapse: collapse;
    border-spacing: 0
  }

  table {
    width: 100%;
  }

  td,
  th {
    border: 1px solid #bcbcbc;
    padding: 5px 10px
  }

  th {
    background: #42b983;
    font-size: 1.2rem;
    font-weight: 400;
    color: #fff;
    cursor: pointer
  }

  tr:nth-of-type(odd) {
    background: #fff
  }

  tr:nth-of-type(even) {
    background: #eee
  }

  fieldset {
    border: 1px solid #BCBCBC;
    padding: 15px;
  }

  input {
    outline: none
  }

  input[type=text] {
    border: 1px solid #ccc;
    padding: .5rem .3rem;
  }

  input[type=text]:focus {
    border-color: #42b983;
  }

  button {
    display: inline-block;
    border: 0;
    box-sizing: border-box;
    color: #fff;
    font-size: 1em;
    border-radius: .1em;
    line-height: 2em;
    padding: 0 1em;
    transition: .4s ease-out;
    outline: 0;
    text-decoration: none;
  }

  button:hover,
  button:focus {
    opacity: 0.5;
    cursor: pointer;
    transition: .15s ease-in;
  }

  .container {
    padding-left: 15px;
    padding-right: 15px;
    margin: 10px;
  }

  .search-input {
    width: 80%;
  }

  .arrow {
    display: inline-block;
    vertical-align: middle;
    width: 0;
    height: 0;
    margin-left: 5px;
    opacity: 0.66;
  }

  .arrow.asc {
    border-left: 4px solid transparent;
    border-right: 4px solid transparent;
    border-bottom: 4px solid #fff;
  }

  .arrow.dsc {
    border-left: 4px solid transparent;
    border-right: 4px solid transparent;
    border-top: 4px solid #fff;
  }

  .btn {
    display: inline-block;
    border: 0;
    box-sizing: border-box;
    background: #42b983;
    color: #fff;
    border-radius: .1em;
    line-height: 2em;
    padding: 0 2em;
    transition: .4s ease-out;
    border: 1px solid #42b983;
    outline: 0;
    text-decoration: none;
  }

  .btn:hover,
  .btn:focus {
    background: #fff;
    color: #42b983;
    cursor: pointer;
    transition: .15s ease-in;
  }

  .form-group {
    margin: 10px;
  }

  .form-group > label {
    display: inline-block;
    padding-right: 1rem;
    width: 5rem;
    text-align: right;
  }

  .form-group > input,
  .form-group > select {
    display: inline-block;
    height: 2.5rem;
    line-height: 2.5rem;
  }

  .text-center {
    text-align: center;
  }

  .dialog {
    position: fixed;
    left: 50%;
    top: 2em;
    transform: translateX(-50%);
    z-index: 2000;
    visibility: hidden;
    backface-visibility: hidden;
    perspective: 1300px;
  }

  .dialog-active {
    visibility: visible;
  }

  .dialog-active .dialog-content {
    opacity: 1;
    transform: rotateY(0);
  }

  .dialog-active ~ .dialog-overlay {
    opacity: 1;
    visibility: visible;
  }

  .dialog-content {
    border-radius: 3px;
    background: #fff;
    overflow: hidden;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    transition: .5s ease-in-out;
    opacity: 0;
    transform-style: preserve-3d;
    transform: rotateY(-70deg);
  }

  .dialog-header {
    background: #42b983;
    color: #fff;
  }

  .dialog-title {
    margin: 0;
    font-size: 2em;
    text-align: center;
    font-weight: 200;
    line-height: 2em;
  }

  .dialog-body {
    padding: 2em;
  }

  .dialog-footer {
    margin: 0 2em;
    padding: 2em 0;
    text-align: right;
    border-top: 1px solid rgba(0, 0, 0, 0.1);
  }

  .dialog-overlay {
    content: "";
    position: fixed;
    visibility: hidden;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    z-index: 1000;
    opacity: 0;
    background: rgba(0, 0, 0, 0.5);
    transition: all .6s;
  }
</style>
