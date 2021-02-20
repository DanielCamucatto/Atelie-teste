<template>
    <section id="container-header">
        <div class="header">
            <div id="img-banner">
                <Banner/>
                <div id="btns">
                    <button id="login" class="btn">
                        <router-link class="btn" to="/login">LOGIN</router-link>
                    </button>
                    <button id="register" class="btn">CADASTRE-SE</button>
                </div>
            </div>
            <div id="clouds"><img src="../assets/img/clouds.png" alt=""></div>
        </div>
    </section>
</template>

<script>
import Banner from './Banner'

export default {
    components:{
        Banner        
    },
   
    
}
</script>

<style>
    
    #container-header{
        /* border: solid 1px royalblue; */
        background-image: url('../assets/img/background.png');
        background-repeat: no-repeat;
        background-position: top center;
        background-size: cover;
        /* height: 100vh;  */
    }
    .header{
        display: grid;
        grid-template-columns: 1fr 2fr;
        width: 70%;
        margin: auto;
    }
    #img-banner{
        display: flex;
        flex-direction: column;
        align-items: flex-end;
        justify-content: center;
        
    }
    #img-banner svg{
        width: 70%;
        margin-top: 20%;
    }
    #clouds img{
        width: 100%;
        margin-top: 8%;
    }
    #btns{
    padding: 2%;
    width: 70%;
    margin-top: -15%;
    display: flex;
    justify-content: space-around;
    }
    .btn{
    background-color: #E6A714;    
    color: #fff;
    padding: 2%;
    width: 50%;
    margin-right: 5%;
    font-size: 0.7rem;
    white-space: nowrap;
    text-decoration: none;
    border-radius: 5px;
    border: none;
    cursor: pointer;
    }
    @media (min-width: 320px) and (max-width: 480px){
        .header{
            grid-template-columns: 1fr;
            margin: auto;
            
        }
        #clouds{
            display: none;
        }
        #img-banner svg{
            margin: auto;
         }
        #btns{
            margin:auto;
        }
    }
    @media (min-width: 481px) and (max-width: 768px){
        .header{
            grid-template-columns: 1fr 1fr;
        }

        #clouds img{
            width: 100%;
            margin-top: 35%;
        }
        #img-banner svg{
            margin: 5% auto;
        }
        #btns{
            width: 50%;
            position: absolute;
            left: 26%;
            top: 45%;
        }
    }    
</style>