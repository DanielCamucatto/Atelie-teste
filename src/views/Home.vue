<template>
  <div id="container-home">
    <Header/>
    <Main/>
    <Footer/>
  </div>
</template>

<script>
import Header from '../components/Header'
import Main from '../components/Main'
import Footer from '../components/Footer'
export default {
  name: 'home',
  components: {
    Header,
    Main,
    Footer, 
    
  }
}
</script>

<style>
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: lato-bold;
}
@font-face {
  font-family: lato-black;
  src: url('../assets/font/Lato-Black.woff');
}
@font-face {
  font-family: lato-hairline;
  src: url('../assets/font/Lato-Hairline.woff');
}
@font-face {
  font-family: lato-bold;
  src: url('../assets/font/Lato-Bold.woff');
}
@font-face {
  font-family: lato-light;
  src: url('../assets/font/Lato-Light.woff');
}
@font-face {
  font-family: lato-medium;
  src: url('../assets/font/Lato-Medium.woff');
}

</style>
