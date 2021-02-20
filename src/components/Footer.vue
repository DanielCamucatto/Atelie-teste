<template>
  <section id="container-footer">
    <footer>
        <div class="footer-txt">
            <h2>SÓ QUEM VENDE CURTE AS <br> EXPERIÊNCIAS MAIS DIFERENTONAS!</h2>
            <p>Campanha valida de 01/02 a 31/03/2020 Vendas via Business Center e para setor publico não serão válidas. A apuração do mês de agosto será retroativa.Imagens meramente ilustrativas. Realizamos todos os esforços para garantir a precisão das informações, mas não somos responsáveis por qualquer conteúdo editorial, fotográfico ou por erros tipograficos. Todas as imagens são apenas para fins ilustrativos. Para especificações completas de produto, informações de serviços e garantias. Visite www.umbrindenaeuropa.com/saiba. Não fazemos nenhuma representação ou garantia em relação a produto ou serviços de terceiros. Outros nomes de empresas, produtos e serviços podem ser marcas registradas ou marcas de serviço de terceiros © 2020. Todos os direitos reservados.</p>
        </div>
        <BannerFooter id="banner-footer"/>
    </footer>
    <div class="doubt">
            <p>Duvidas? Envie um e-mail para <span>atendimento@umbrindenaeuropa.com.br</span></p>
            <p>Imagens meramente ilustrativas. Promoção valida de 01/02 a 31/03/2020.</p>
        </div>
  </section>
</template>

<script>
import BannerFooter from './BannerFooter'
export default {

    components:{
        BannerFooter    
    }
}
</script>

<style>
    footer{
        background-image: url("../assets/img/background-cinza.png");
        display: grid;
        grid-template-columns: 2fr 1fr;
    }
    h2{
        color:#383C3D;
        text-align: left;
        margin: 5% auto 0px;
        width: 100%;
        font-family: lato-light;
        font-size: 1.2rem;
        letter-spacing: 4px;
        padding-left: 3%;
    }
    .footer-txt{
        margin-left: auto;
        padding-left: 25%;
        width: 100%;
    }
    .footer-txt p{
        color: #383C3D;
        margin-left: auto;
        width: 100%;
        text-align: justify;
        font-size: 0.6rem;
    }
    .doubt{
        border: solid 1px white;
        background-color:#E6A714;
        display: flex;
        align-items: center;
        height: 13vh;
    }
    .doubt p{
        color: white;
        white-space: nowrap;
        font-size: 0.7rem;
        font-family: lato-light;
    }
    .doubt p > span{
        color: #383C3D;
    }
 @media (min-width: 320px) and (max-width: 480px){
    footer{
        grid-template-columns: 1fr
    }
    .footer-txt{
        margin: auto!important; 
        padding-left: 0px!important;
        width: 90%;
    }
    footer h2{
        width: 100%;
        margin: 5% auto; 
        text-align: center;
        font-size: 0.5rem;
       }
       
       #banner-footer{
            display: none
       }
    .doubt{
        flex-direction: column;
        height: 10%;
        width: 100%
    }
    .doubt p{
        width: 90%;
        font-size: 0.5rem;
    }

 }
 @media (min-width: 481px) and (max-width: 768px){
    footer{
        grid-template-columns: 2fr 1fr;
        grid-gap: 5% ;
    }
    .footer-txt{
        margin: auto!important;
        padding: 0px;
    }
    h2{    
        font-size: 0.8rem;
        width: 100%; 
    }
    .doubt p {    
        white-space: normal
    }
 }
</style>