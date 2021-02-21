<template>
<div>
<Header/>
<section id="container-login">
      <h1>LOGIN</h1>
      <form id="form-login" action="">
          <input type="text" name="cpf" id="cpf" placeholder="Digite seu CPF">
          <input type="text" name="password" id="password" placeholder="Digite sua Senha">
          <div class="questions">
              <small><router-link to="/" class="registered">Ainda não é cadastrado?</router-link></small>
              <small @click="forgotPass">Esqueceu sua senha?</small> 
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
        
    },
    methods:{
        forgotPass(){
            this.$swal({
                title: '<h2>Esqueceu sua senha?</h2>',
                text: 'Digite seu e-mail para redefinir sua senha (mandaremos o link para lá)',
                input: 'email'

            })
            
        }
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
    #form-login{
        width: 50%;
        margin: auto;
    }
    
    .questions{
        display: flex;
        justify-content: space-between;
        width: 80%;
        margin-top: 2%;
        color: #E6A714;
        font-size: 0.8rem;
        cursor: pointer;    
    }
    small:hover{
        border-bottom: solid 1px #E6A714;
    }
    .registered{
        color: #E6A714;
        text-decoration: none;
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
    .swal2-popup{
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        align-items: center;
    }
    .swal2-popup h2{
        white-space: nowrap;
        margin-bottom: 5%;
    }
    .swal2-popup input{
        margin: 5% auto;
    }
    .swal2-popup button{
        border: none;
        padding: 0 100%;
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