<template>
  <div class="privacy">
    <div class="header2 light">
      Privacy Policy
    </div>  
    <div class="policy bodyText">
      <p>FLYTA collects absolutely zero personal information from its users.</p>


  </div>

  </div>
</template>

<script>
export default {
  name: 'Privacy',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
@import '../style.scss';


  .privacy{
    color: white;
    text-align: center;
    margin: 0 auto;
    padding-top: 200px;
    font-family: 'Optician-Sans';
  }

  .policy{
  }

</style>
