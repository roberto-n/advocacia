<template>
  <div>
    <nav class="containernav">
      <img class="logo" src="../assets/logo.png" alt="" />
      <a class="nav" href="">Areas de atuaçao</a>
      <a  class="nav" href="">Advogados</a>
      <a class="nav" href="">Contato</a>
    </nav>
    <body>
    <transition-group name="fade" tag="div" >
       <template > 
      <div v-for="i in [indexAtual]" :key="i" class="containerarea">
        <img :src="currentImg" />
        
        <div class="area" >{{currentArea}}</div>
      
      </div>
      </template>
    </transition-group>
    <h2 class="titulos">Advogados</h2>
    <div class="advogadochef">
      <img  class="imgadvogadochef" src="../assets/advogado1.jpg" alt="" />
      <h3>Advogado Senior <br> Nome:XXXXXXXXXX <br>Especialista Em :Direito XXXXX</h3>
      </div>
    <div class="containeradvogados">
       <div class="advogado1">
        <img class="imgadvogados" src="../assets/advogado2.jpg" alt="" />
        <h3>Nome:XXXXXXXXXX <br> Especialista Em :Direito XXXXX</h3>
       </div>
       <div class="advogado2">
        <img class="imgadvogados"  src="../assets/advogado3.jpg" alt="" />
        <h3>Nome:XXXXXXXXXX <br> Especialista Em :Direito XXXXX</h3>
       </div>
      <div class="advogado3" >
        <img  class="imgadvogados" src="../assets/advogada1.jpg" alt="" />
        <h3>Nome:XXXXXXXXXX <br>  Especialista Em :Direito XXXXX</h3>
      </div>
      <div class="advogado4" >
       <img  class="imgadvogados" src="../assets/advogada2.jpg" alt="" />
       <h3>Nome:XXXXXXXXXX <br> Especialista Em :Direito XXXXX</h3>
      </div>
    </div>
    <h2 class="titulos">Depoimentos</h2>
    <div class="containerdepoimentos">
      <div class="depoimento1">
       <img class="imgdepoimento" src="../assets/depoimento1.jpg" alt="" />
       <h3>
        "Nome:XXXXXXXXXX <br> Obrigado a Infinity Advocacia por me ajudar em
        :XXXXXXXXXX"
       </h3>
      </div>
      <div class="depoimento2">
       <img class="imgdepoimento" src="../assets/depoimento2.jpg" alt="" />
       <h3>
        "Nome:XXXXXXXXXX <br> Obrigado a Infinity Advocacia por me ajudar em
        :XXXXXXXXXX"
       </h3>
      </div>
      <div class="depoimento3">
      <img  class="imgdepoimento" src="../assets/depoimento3.jpg" alt="" />
       <h3>
        "Nome:XXXXXXXXXX <br>  Obrigado a Infinity Advocacia por me ajudar em
        :XXXXXXXXXX"
       </h3>
      </div>
      <div class="depoimento4">
       <img class="imgdepoimento" src="../assets/depoimento4.jpg" alt="" />
       <h3>
        "Nome:XXXXXXXXXX <br> Obrigado a Infinity Advocacia por me ajudar em
        :XXXXXXXXXX"
       </h3>
      </div>
      <div class="depoimento5">
       <img class="imgdepoimento" src="../assets/depoimento5.jpg" alt="" />
       <h3>
        "Nome:XXXXXXXXXX <br> Obrigado a Infinity Advocacia por me ajudar em
        :XXXXXXXXXX"
       </h3>
      </div>
    </div>
    </body>
    <footer>Criado por</footer>
  </div>
</template>
<script>
export default {
  name: "Slider",
  data() {
    return {
      images: [
        'img/area1.jpg',
        "img/area5.jpg",
        "img/area8.jpg",
        "img/area10.png",
        "img/area13.jpg",
        "img/area14.jpg",
      ],
      timer: null,
      indexAtual: 0,
      areas: [
        "Direito Imobiliario",
        "Direito Civil",
        "Direito Familiar",
        "Direito Edicacional",
        "Direito Adiministrativo",
        "Direito Empresarial",
         ]
    };
  },
  mounted: function() {
    this.startSlide();
  },
  methods: {
    startSlide: function() {
      this.timer = setInterval(this.proximo, 9000);
    },
    proximo: function() {
      this.indexAtual += 1;
    },

  },
  computed: {
    currentImg: function() {
      return this.images[Math.abs(this.indexAtual) % this.images.length];
    },
    currentArea: function() {
      return this.areas[Math.abs(this.indexAtual) % this.images.length];
    }
  }
};
</script>
<style>
.fade-enter-active,
.fade-leave-active {
  transition: all 0.9s ease;
  overflow: hidden;
  visibility: visible;
  width:100%;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: visible;
  width:100%;
  opacity: 0;
}

img {
  height:300px;
  width:100%
}


.containernav{
  display: flex;
  justify-content: space-between;
   align-items: center;
   background-color:#c2c2b9;
}
.logo {
  height: 50px;
  width: 550px;
  margin: 5px;
  
}
.nav{
  margin: 5px;
}
.containerarea {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 300px;
  width:100%;
  overflow: hidden;

}
.area{
  position: absolute;
  text-align: center;
  color: white;
  background-color: rgb(0,0,0,0.9);
}
.containeradvogados {
   display: grid;
    grid-template-columns:1fr 1fr ;
    grid-template-rows:1fr 1fr ;
  width: 100%;
  justify-items:start ;
  grid-template-areas: "advogados1  advogados2"
                       "advogados3  advogados4"
                       ;
  background-color:#e4d5d5;
  margin: 10px;
   row-gap: 10px;
}

.advogado1{
   display: flex;
  justify-content:center;
  align-items: center;
  height: 200px;
   justify-self: center;
  grid-area:advogados1;
}

.advogado2{
  display: flex;
  justify-content:center;
  align-items: center;
  height: 200px;
   justify-self: center;
  grid-area:advogados2;
}
.advogado3{
   display: flex;
  justify-content:center;
  align-items: center;
  height: 200px;
   justify-self: center;
  grid-area:advogados3;
}
.advogado4{
   display: flex;
  justify-content:center;
  align-items: center;
  height: 200px;
   justify-self: center;
  grid-area:advogados4;
}


.advogadochef{
  display: flex;
  justify-content:center;
  align-items: center;
  height: 220px;
  padding: 0 0 0 150px;
}
.imgadvogadochef{
   height: 200px;
  width: 200px;
  border-radius: 50%;
}
.imgadvogados{
  border-radius: 50%;
   height: 200px;
  width: 150px;
  margin: 10px;
}
  .containerdepoimentos{
  display: grid;
  grid-template-columns:1fr 1fr 1fr;
  grid-template-rows:1fr 1fr 1fr 1fr;
  grid-template-areas:".depoimento1."
                      "depoimento2.depoimento3"
                      ".depoimento4."
                      ".depoimento5."
  ;
  width: 100%;
  }
 .depoimento1{
   display: flex;
   align-items: center;
   grid-area:depoimento1;
   justify-self: center;
 }
  .depoimento2{
  display: flex;
  align-items: center;
   grid-area:depoimento2;
   justify-self: center;
 }
  .depoimento3{
    display: flex;
    align-items: center;
   grid-area:depoimento3;
   justify-self: center;
 }
  .depoimento4{
   display: flex;
   align-items: center;
   grid-area:depoimento4;
   justify-self: center;
   margin: 0 0 5px 0 ;
 }
  .depoimento5{
   display: flex;
   align-items: center;
   grid-area:depoimento5;
   justify-self: center;
 }
 .imgdepoimento{
   border-radius: 50%;
  margin: 5px 5px 5px 5px;
  height: 125px;
  

 }
  .titulos{
    display: flex;
    justify-content:center;
    align-items: center;
    height: 50px;
    background-color:#000080;
    margin: 0 0 0 0;
    color: rgb(255, 241, 240);
  }
  body{
    background-color:#e4d5d5;}
</style>