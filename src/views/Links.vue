<template>
  <div id="app">
    <img :src="myLogo" id="myLogo">
    
    <!-- box menu -->
    <div class="menu">
      <!-- menu btn -->
      <div class="menuBtn" @click="gotted()">
        <div :class="slash1"></div>
        <div :class="slash2"></div>
        <div :class="slash3"></div>
      </div>
      
      <!-- my links -->
      <a :href="github" target="_blank" :class="got" class="github"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><g fill="#181616"><path fill-rule="evenodd" clip-rule="evenodd" d="M64 5.103c-33.347 0-60.388 27.035-60.388 60.388 0 26.682 17.303 49.317 41.297 57.303 3.017.56 4.125-1.31 4.125-2.905 0-1.44-.056-6.197-.082-11.243-16.8 3.653-20.345-7.125-20.345-7.125-2.747-6.98-6.705-8.836-6.705-8.836-5.48-3.748.413-3.67.413-3.67 6.063.425 9.257 6.223 9.257 6.223 5.386 9.23 14.127 6.562 17.573 5.02.542-3.903 2.107-6.568 3.834-8.076-13.413-1.525-27.514-6.704-27.514-29.843 0-6.593 2.36-11.98 6.223-16.21-.628-1.52-2.695-7.662.584-15.98 0 0 5.07-1.623 16.61 6.19C53.7 35 58.867 34.327 64 34.304c5.13.023 10.3.694 15.127 2.033 11.526-7.813 16.59-6.19 16.59-6.19 3.287 8.317 1.22 14.46.593 15.98 3.872 4.23 6.215 9.617 6.215 16.21 0 23.194-14.127 28.3-27.574 29.796 2.167 1.874 4.097 5.55 4.097 11.183 0 8.08-.07 14.583-.07 16.572 0 1.607 1.088 3.49 4.148 2.897 23.98-7.994 41.263-30.622 41.263-57.294C124.388 32.14 97.35 5.104 64 5.104z"/><path d="M26.484 91.806c-.133.3-.605.39-1.035.185-.44-.196-.685-.605-.543-.906.13-.31.603-.395 1.04-.188.44.197.69.61.537.91zm2.446 2.729c-.287.267-.85.143-1.232-.28-.396-.42-.47-.983-.177-1.254.298-.266.844-.14 1.24.28.394.426.472.984.17 1.255zM31.312 98.012c-.37.258-.976.017-1.35-.52-.37-.538-.37-1.183.01-1.44.373-.258.97-.025 1.35.507.368.545.368 1.19-.01 1.452zm3.261 3.361c-.33.365-1.036.267-1.552-.23-.527-.487-.674-1.18-.343-1.544.336-.366 1.045-.264 1.564.23.527.486.686 1.18.333 1.543zm4.5 1.951c-.147.473-.825.688-1.51.486-.683-.207-1.13-.76-.99-1.238.14-.477.823-.7 1.512-.485.683.206 1.13.756.988 1.237zm4.943.361c.017.498-.563.91-1.28.92-.723.017-1.308-.387-1.315-.877 0-.503.568-.91 1.29-.924.717-.013 1.306.387 1.306.88zm4.598-.782c.086.485-.413.984-1.126 1.117-.7.13-1.35-.172-1.44-.653-.086-.498.422-.997 1.122-1.126.714-.123 1.354.17 1.444.663zm0 0"/></g></svg></a>
      <a :href="linkedin" target="_blank" :class="got" class="linkedin"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 128 128"><defs></defs><g id="original"><path class="cls-1" d="M116,3H12a8.91,8.91,0,0,0-9,8.8V116.22A8.91,8.91,0,0,0,12,125H116a8.93,8.93,0,0,0,9-8.81V11.77A8.93,8.93,0,0,0,116,3Z"/><path class="cls-2" d="M21.06,48.73H39.17V107H21.06Zm9.06-29a10.5,10.5,0,1,1-10.5,10.49,10.5,10.5,0,0,1,10.5-10.49"/><path class="cls-2" d="M50.53,48.73H67.89v8h.24c2.42-4.58,8.32-9.41,17.13-9.41C103.6,47.28,107,59.35,107,75v32H88.89V78.65c0-6.75-.12-15.44-9.41-15.44s-10.87,7.36-10.87,15V107H50.53Z"/></g></svg></a>
      <a :href="codepen" target="_blank" :class="got" class="codepen"><svg viewBox="0 0 128 128" fill="none" xmlns="http://www.w3.org/2000/svg">
<path d="M125.571 39.926L67.0715 0.925997C65.0744 -0.303094 62.9434 -0.314225 60.9285 0.925997L2.42867 39.926C0.928561 40.9256 0 42.712 0 44.4971V83.4971C0 85.2827 0.928561 87.0686 2.42895 88.0682L60.9288 127.074C62.9254 128.303 65.0566 128.314 67.0715 127.074L125.571 88.0682C127.071 87.0692 128 85.2827 128 83.4971V44.4971C128 42.712 127.071 40.9256 125.571 39.926ZM69.5001 15.7825L112.571 44.4971L93.3566 57.3548L69.5001 41.4259V15.7825ZM58.4999 15.7825V41.4256L34.6422 57.3545L15.4285 44.4968L58.4999 15.7825ZM10.9997 54.7828L24.7856 63.9972L10.9997 73.2117V54.7828ZM58.4999 112.212L15.4285 83.4971L34.6422 70.6399L58.4999 86.5689V112.212ZM64 76.9966L44.5715 63.9972L64 50.997L83.4285 63.997L64 76.9966ZM69.5001 112.212V86.5692L93.3566 70.6402L112.571 83.4974L69.5001 112.212ZM117 73.2117L103.214 63.9972L117 54.7828V73.2117Z" fill="black"/>
</svg></a>
      <a :href="website" target="_blank" :class="got" class="website"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 496 512"><path d="M336.5 160C322 70.7 287.8 8 248 8s-74 62.7-88.5 152h177zM152 256c0 22.2 1.2 43.5 3.3 64h185.3c2.1-20.5 3.3-41.8 3.3-64s-1.2-43.5-3.3-64H155.3c-2.1 20.5-3.3 41.8-3.3 64zm324.7-96c-28.6-67.9-86.5-120.4-158-141.6 24.4 33.8 41.2 84.7 50 141.6h108zM177.2 18.4C105.8 39.6 47.8 92.1 19.3 160h108c8.7-56.9 25.5-107.8 49.9-141.6zM487.4 192H372.7c2.1 21 3.3 42.5 3.3 64s-1.2 43-3.3 64h114.6c5.5-20.5 8.6-41.8 8.6-64s-3.1-43.5-8.5-64zM120 256c0-21.5 1.2-43 3.3-64H8.6C3.2 212.5 0 233.8 0 256s3.2 43.5 8.6 64h114.6c-2-21-3.2-42.5-3.2-64zm39.5 96c14.5 89.3 48.7 152 88.5 152s74-62.7 88.5-152h-177zm159.3 141.6c71.4-21.2 129.4-73.7 158-141.6h-108c-8.8 56.9-25.6 107.8-50 141.6zM19.3 352c28.6 67.9 86.5 120.4 158 141.6-24.4-33.8-41.2-84.7-50-141.6h-108z"/></svg></a>
      <a :href="youtube" target="_blank" :class="got" class="youtube"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 32.002 22.746"><path d="M27.671,0.419c-7.286-0.49-15.924-0.624-23.344,0C2.023,0.677,0.445,3.481,0.273,5.611c-0.364,4.474-0.364,7.02,0,11.494c0.174,2.13,1.712,4.95,4.056,5.246c7.508,0.492,16.102,0.56,23.344,0c2.268-0.394,3.882-3.116,4.056-5.246c0.364-4.474,0.364-7.298,0-11.774C31.553,3.201,30.281,0.515,27.671,0.419z M11.999,17.033V5.563l10,5.736L11.999,17.033z"/></svg></a>
      
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      got: '',
      isGot: true,
      
      slash1: '',
      slash2: '',
      slash3: '',
      
      linkedin: 'https://www.linkedin.com/in/isaac-louzeiro/',
      github: 'https://github.com/IsaacLouzeiro',
      codepen: 'https://codepen.io/isaaclouzeiro/',
      website: 'https://isaaclouzeiro.dev.br/',
      youtube: 'https://www.youtube.com/c/isaaclouzeirodev',
      
      myLogo: 'https://github.com/IsaacLouzeiro/My-Codepen-Database-Images/blob/master/minha-logo-isaac-louzeiro.png?raw=true'
    }
  },
  
  methods: {
    gotted() {
      this.isGot = !this.isGot;
      
      if(this.isGot == false) {
        this.got = "got";
        this.slash1 = "slash1";
        this.slash2 = "slash2";
        this.slash3 = "slash3";
      }else {
        this.got = "";
        this.slash1 = "";
        this.slash2 = "";
        this.slash3 = "";
      }
    }
  }
};
</script>

<style lang="scss">
  $color1: #e8e8e6;
  $color2: #212528;
  $color3: #004B63;
  $color4: #ff7a4f;
  
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  html, body, #app {
    width: 100%;
    height: 100%;
  }
  
  #app {
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    background-color: $color1;
    min-height: 500px;
    
    // background
    #myLogo {
      width: 300px;
      height: 300px;
      position: absolute;
      opacity: .2;
    }
    
    // box menu
    .menu, .menuBtn {
      width: 60px;
      height: 60px;
      border-radius: 30px;
      position: relative;
      z-index: 99999;
      background-color: $color2;
      cursor: pointer;
    }
    
    // menu btn
    .menuBtn {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      div {
        width: 30px;
        margin: 2px 0;
        border: 2px solid $color1;
        background-color: $color1;
        border-radius: 2px;
        position: relative;
        transition: all .5s;
        
        &.slash1 { transform: rotate(45deg); top: 8px; }
        &.slash2 { transform: rotate(45deg); }
        &.slash3 { transform: rotate(-45deg); top: -8px; }
        
      }
    }
    
    
    // my links
    a {
      position: absolute;
      transform: rotate(180deg);
      transition: all .3s;
      left: 0;
      right: 0;
      top: 0;
      bottom: 0;
      margin: auto;
      display: inline-block;
      width: 55px;
      height: 55px;
      border-radius: 30px;
      z-index: 0;
      display: flex;
      justify-content: center;
      background-color: $color4;
      
      // width of the icons
      svg {
        width: 30px;
      }
      
      // svg linkedin color
      .cls-1{fill: $color2;}.cls-2{fill: $color4;}
    
      &.got {
        &.github { transform: rotate(0deg) translateY(80px); transition-delay: calc(.2s); svg{ path { fill: $color2; } } }
        &.youtube { transform:  rotate(0deg) translateY(160px); transition-delay: calc(.4s); svg{ path { fill: $color2; } } }
        &.linkedin { transform:  rotate(0deg) translateX(80px); transition-delay: calc(.6s); }
        &.website { transform:  rotate(0deg) translateY(-80px); transition-delay: calc(.8s); svg { fill: $color2; } }
        &.codepen { transform:  rotate(0deg) translateX(-80px); transition-delay: calc(.10s); svg{ path { fill: $color2; } } }
      }
    }
  }
</style>