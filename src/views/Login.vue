<template>
<div>
<Header/>
<section id="container-login">
      <h1>LOGIN</h1>
      <form action="">
          <input type="text" name="cpf" id="cpf" placeholder="Digite seu CPF">
          <input type="text" name="password" id="password" placeholder="Digite sua Senha">
          <div class="questions">
              <small>Ainda não é cadastrado?</small>
              <small>Esqueceu sua senha?</small>
          </div>
          <button id="btn-login">ENTRAR</button>
      </form>
  </section>
<Footer/>
</div>
  
</template>

<script>
import Header from '../components/Header'
import Footer from '../components/Footer'

export default {
    name: 'login',
    components:{
        Header,
        Footer
        
    }
}
</script>

<style>
    #container-login{
        background-image: url('../assets/img/background-marrom.png');
        color: white;
        height: 60vh;
        }
    h1{
        text-align: center;
        margin-top: 3%;
        font-size: 2rem;
        padding-top: 40px;
    }
    form{
        margin: 3% auto;
        width: 40%;
    }
    form input{
        width: 80%;
        margin-top: 10% ;
    }
    .questions{
        display: flex;
        justify-content: space-between;
        width: 100%;
        margin-top: 2%;
        color: #E6A714;
        font-size: 0.8rem;
        cursor: pointer;    
    }
    small:hover{
        border-bottom: solid 1px #E6A714;
    }
    #btn-login{
        margin: 3% auto;
        background-color: #E6A714;
        border: none;
        border-radius: 5px;
        color: white;
        padding: 1% 3%;
        display: block;
        cursor: pointer;
        transition: 100ms;
    }
    #btn-login:hover{
        background-color: yellow;
    }
     @media (min-width: 320px) and (max-width: 480px){
        #container-login{
            height: 40vh
        }
        form{
            width: 90%
         }
     }
     @media (min-width: 481px) and (max-width: 768px){
        #container-login{
            height: 40vh
        }
        form{
            width: 80%
        }
     }
</style>