<template>
  <div class="support">
    <div class="header2 dark">
      Support
    </div>  
    <div class="contact bodyText">
      <p>For any questions or comments, please email us at </p> 
      <a class="primary" href="mailto: support@flytagame.com">support@flytagame.com</a>
      <p>we will try to respond as quickly as possible.</p>


  </div>

  </div>
</template>

<script>
export default {
  name: 'Support',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import '../style.scss';


  .support{
    background-color: white;
    color: $dark;
    text-align: center;
    margin: 0 auto;
    margin-top: 200px;
    font-family: 'Optician-Sans';
  }

  .contact{
  }

</style>
