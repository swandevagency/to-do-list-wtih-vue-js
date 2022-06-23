<template>
  <hero>
    <div class="left-part-of-hero">
      <p>Who We Are</p>
      <h1>Helping you to have a better disipline</h1>
      <p class="sub-header">Lorem ipsum dolor sit amet, consectetur adipiscing elit,</p>
    </div>
    <div class="right-part-of-hero">
      
    </div>
  </hero>

  <section>
    <div>
      
    </div>
  </section>
</template>

<style lang="scss">
*{
  margin: 0;
}

hero{
  width: 100%;
  display: flex;
  padding: 0px 60px;
}

.right-part-of-hero{
  width: 47%;
  height: 65vh;
  background: url('@/assets/hero.png');
  background-size: cover;
}

.left-part-of-hero{
  width: 50%;
    
  h1{
    color: #16697B;
    font-weight: bolder;
    padding-right: 170px;
    font-size: 60px;
    line-height: 65px;
   
  }

  p{
    color: #82C1CE;
    margin-top: 50px;
    margin-left: 5px;
    font-size: 22px;
  }

  .sub-header{
    color: #4A95A5;
    margin-top: 40px;
    margin-left: 5px;
    font-size: 24px;
  }
}

</style>
