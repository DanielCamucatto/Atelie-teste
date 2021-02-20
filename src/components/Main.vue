<template>
  <section id="container-main">
    <h1>CADASTRE-SE</h1>
    <p>Preencha os campos a baixo para validar sua participação na campanha e concorrer a prêmios</p>
      <form @submit.prevent="submitForm">
      <label for="name">Nome</label>
      <input type="text" name="name" id="name" placeholder="Nome" v-model="form.name">
      <small class="error" v-show="error">Dado incorreto, insira novamente</small>
      <div id="cols">
      <fieldset class="col-form">
        <label for="cpf">CPF</label>
        <input type="text" name="cpf" id="cpf" placeholder="000.0000.000-00" v-model="form.cpf">
        <small class="error" v-show="error">Dado incorreto, insira novamente</small>
        <label for="password">Senha</label>
        <input type="password" name="password" id="password" placeholder="Senha" v-model="form.password">
        <small class="error" v-show="error">Dado incorreto, insira novamente</small>
        <label for="company">Empresa</label>
        <input type="text" name="company" id="company" placeholder="Empresa" v-model="form.company">
        <small class="error" v-show="error">Dado incorreto, insira novamente</small>
      </fieldset>
      <fieldset class="col-form">
        <label for="email">E-mail</label>
        <input type="email" name="email" id="email" placeholder="E-mail" v-model="form.email">
        <small class="error" v-show="error">Dado incorreto, insira novamente</small>
        <label for="confim">Senha</label>
        <input type="password" name="confirm" id="confirm" placeholder="Confirme sua senha" v-model="form.confim">
        <small class="error" v-show="error">Dado incorreto, insira novamente</small>
        <label for="classification">Classificação</label>
        <select name="classification" id="classification" v-model="form.classification">
          <option value="">Escolha sua categoria</option>
          <option value="">Gerente</option>
          <option value="">Revendedor</option>
          <option value="">Distribuidor</option>
        </select>
      </fieldset>
      
      </div>
    </form>
    <button type="submit" id="btn" @click="submitForm">Enviar</button>
  </section>
</template>

<script>
 import axios from 'axios'
 //import {required} from 'vuelidate/lib/validators'
 
export default {
  data(){
    return{
      error: false,
      form :{
        name: "",
        cpf: "",
        email: "",
        password: "", 
        confirm: "",
        company: "", 
        classification: "" 
      },
      
    }
  },
  
  methods: {
    submitForm(){
      if(this.form.name == "" || this.form.name == " " || this.form.name.length < 3){
        if(this.form.cpf == "" || this.form.cpf == " " || this.form.cpf.length < 12){
          if(this.form.email == "" || this.form.email == " "){
            if(this.form.password == "" || this.form.password == " "){
              if(this.confirm == "" || this.form.confirm == " " || this.form.confirm === this.form.password){
                if(this.form.company == "" || this.form.company == " "){
                  this.error = true
                }
              }
            }
          }
        }
      }else{
        axios.post('https://virtserver.swaggerhub.com/ateliedepropaganda/register/1.0.0/costumer', this.form)
      .then(resp => {
        console.log(resp)
        
      })
      this.alertDisplay()
      }  
    },
      
    alertDisplay(){
      this.$swal({
        title: "<h3>Cadastro realizado com sucesso!</h3>", 
        showCloseButton: true, 
        showConfirmButton: false,
      })
    }  
  }

}
</script>

<style>
    #container-main{
        background-image: url('../assets/img/background-marrom.png');
        /* background-repeat: no-repeat; */
        height: 80vh;
        color: white;
    }
    h1{
      text-align: center;
      margin-top: 3%;
      font-size: 2rem;
      padding-top: 40px;
    }
    p{
    text-align: center;
    margin: -2% auto;
    width: 40%;
    padding: 3%;
    font-size: 1rem;
    font-weight: 500;
    }
    
    form{
      margin:  -3% auto;
      width: 50%;
      padding: 0px 3%;
    }
    #cols{
      display: grid;
      grid-template-columns: 1fr 1fr;
      margin: auto;
    }
    .col-form{
      display: flex;
      flex-direction: column;
    }
    fieldset{
      border: none;
      margin-top: 2%;
    }
    label{
      display: block;
      margin-top: 5%;
      font-size: 0.8rem;
    }
    input{
      outline: 0;
      background-color: #0000;
      border: none;
      border-bottom: solid 1px #fff;
      width: 80%;
      margin-top: 1%;
    }
    #name{
      width: 90%;
    }
    input:hover{
      border-bottom: solid 1px #E6A714 ;
    }
   input::-webkit-input-placeholder{
     color: white;
     font-size: 18px;
   }
   input::-moz-placeholder{
     color: white;
     font-size: 18px;
   }
    select{
      background-color: #0000;
      color: white;
      border: none;
      outline: none;
      border-bottom: solid 1px white;
      width: 80%;
    }  
  select:hover,
  select:focus,
  select:active,
  select:focus {
  color: white;
  transition:0s;
  border-bottom: solid 1px white;
  }
  #btn{
    background-color: #E6A714;
    color: #fff;
    border: none;
    padding: 2px 3%;
    border-radius: 3px;
    display: block;
    margin: 4% auto 0%;
    font-size: 1rem;
    cursor: pointer;  
  } 
  #btn:hover{
    background-color: yellow;
  }
  .swal2-popup{
    background-color: #E6A714;
    color: white;
    position: absolute;
    top: 115%;
    left: 35%;
    padding: 2%;
  } 
  .swal2-popup h3{
    color: white;
    white-space: nowrap;
  }
  .swal2-close{
  position: relative;
  top: -71%;
  left: 97%;
  font-size: 150%;
  padding: 3%;
  color: white;
  background-color: #E6A714;
  border: none;
  }
  .error{
    color: red;
    display: block;
  }
  @media (min-width: 320px) and (max-width: 480px){
    #container-main{
      height: 80vh
    }
    p{
      width: 100%;
    }
    form{
      width: 100%;
    }
    #cols{
      width: 100%;
      display: block;
    }
    #btn{
      margin: 5vh auto;
    }
  }
  @media (min-width: 481px) and (max-width: 768px){
    #container-main{
      height: 80vh
    }
    p{
      width: 100%;
    }
    form{
      width: 100%;
    }
    #name{
      width: 80%;
    }
    #cols{
      width: 100%;
      display: block;
    }
    #btn{
      margin: 5vh auto;
    }
  
}

</style>