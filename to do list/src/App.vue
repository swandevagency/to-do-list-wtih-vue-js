<script setup>
  
</script>

<template>
  <header>
    <div  class="header-logo">
      <img alt="Vue logo" src="@/assets/logo.svg" width="125" height="125" />
    </div>
    
    <nav class="navbar-wrapper">
      <RouterLink to="/">Home</RouterLink>
      <RouterLink to="/about">About</RouterLink>
      <a>Blog</a>
      <a>Sign in</a>
      <a class="navbar-signup">Sign up</a>
    </nav>
  </header>
  <RouterView />
  <footer>
    <div class="footer-section-wrapper">
      <div>
        <div class="footer-logo">
          <img alt="Vue logo" src="@/assets/logo.svg" width="125" height="125" />
        </div>
        <p>have discipline in your life</p>
      </div>
      <div>
        <h5>Title 1</h5>
        <p>page 1</p>
        <p>page 2</p>
        <p>page 3</p>
        <p>page 4</p>
      </div>
      <div>
        <h5>Title 2</h5>
        <p>page 1</p>
        <p>page 2</p>
        <p>page 3</p>
        <p>page 4</p>
      </div>
      <div>
        <h5>Title 3</h5>
        <p>page 1</p>
        <p>page 2</p>
        <p>page 3</p>
        <p>page 4</p>
      </div>
      <div>
        <h5>Title 4</h5>
        <p>page 1</p>
        <p>page 2</p>
        <p>page 3</p>
        <p>page 4</p>
      </div>
    </div>
  </footer>
  
</template>

<style lang="scss">
@import '@/assets/base.css';
body{
  background-color: rgb(255, 255, 255);
}

header{
  display: flex;
  flex-flow: row nowrap;
  width: 100%;
  border-bottom: #C3E6F1 1px solid;
  justify-content: space-between
}

.wrapper{
  display: flex;
  flex-flow: row nowrap;
}

.header-logo{
  width: 10%;
  text-align: center;
  img{
    width: 40px;
    height: 60px;
  }
}
.navbar-wrapper{
  width: 55%;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-evenly;
  padding: 14px 0px;
  line-height: 35px;

  a{
    text-decoration: none;
    color: #004655;
    font-weight: bold;
    font-size: 16px;
  }
  a:hover{
    color: #30a0b8;
  }
}

.navbar-signup{
  background-color: #FFF510;
  padding: 0px 10px;
  border-radius: 5px;
  box-shadow: 2px 2px #d5d5d5;
}

.navbar-signup:hover{
  box-shadow: 0px 0px #e8e8e8;
}






footer{
  width: 100%;
  background-color: #004655;
}

.footer-section-wrapper{
  height: 100%;
      padding: 60px 90px 30px 60px;
  display: flex;
  flex-flow: row nowrap;
  justify-content: space-between;

  h5{
    font-size: 20px;
    font-weight: 700;

  }

  div{
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  & div:first-child{
    align-items: flex-start;
  }

  h5{
        margin: 20px 0px;
  }
}

.footer-logo{
  width: 10%;
  text-align: center;
  img{
    width: 40px;
    height: 60px;
  }
}

</style>
