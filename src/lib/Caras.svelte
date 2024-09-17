<script>
    import * as d3 from "d3"

 //import textos from "./data/textos.json"

    export let title = ""
    export let numbers = []
    export let numbers2 = []
    export let years=[]
    let numbersDivided1 = numbers.map(n => Math.floor(n / 1))
    let totalVisitantes = 1010;
    let visitantesVerano = 635;
    let visitantesInvierno = 375;
    
    // let colorLightness = d3
    //.scaleLinear()
    //.domain([0, d3.max(data)])
    //.range(["white", "#EE0001"])

    let opacityScale = d3
    .scaleLinear()
    .domain([0, 100]) // valores de numbers
    .range([0.2, 1]); // opacidad mínima y máxima

    let opacityScale2 = d3
    .scaleLinear()
    .domain([0, 100]) // valores de numbers
    .range([0.2, 1]); // opacidad mínima y máxima

    let images = [
    "./images/verano11.svg",
    "./images/verano22.svg",
    "./images/verano33.svg",
    "./images/verano55.svg",
    "./images/verano44.svg"
  ];

let imagesdos = [
  "./images/invierno11.svg",
  "./images/invierno22.svg",
  "./images/invierno33.svg",
  "./images/invierno44.svg",
  "./images/invierno55.svg"
];



  function getRandomImage1() {
    return images[Math.floor(Math.random() * images.length)];
  }

  function getRandomImage2() {
    return imagesdos[Math.floor(Math.random() * imagesdos.length)];
  }

  function scrollToTop() {
    window.scrollTo({ top: 0, behavior: 'smooth' });
  }

  </script>
  

<!-- Título, subtítulo y bajada -->
<h1 class="titulo">Chau Nieve, <br>hola Sol!</h1>
<h2 class="subtitulo">Con la nieve en retirada, los viajeros cambian los abrigos por trajes de baño. Los destinos de verano ganan terreno mientras los amantes del frío se quedan con ganas de más.</h2>


<div class="escala">
<img src="./images/escala.svg" alt="escala">
</div>


<div class="rectangulo">
  La historia comienza en un mundo donde cada vez más gente busca reconectar con la naturaleza, eligiendo entre destinos invernales y de verano. Durante mucho tiempo, los paisajes nevados llevaban la ventaja, atrayendo a quienes anhelaban vacaciones frías.
</div>

<h3 class="headline">{title}</h3>

<div class="titulos">
  <h3>Destinos de veraneo</h3>
  <h3>Destinos invernales</h3>
</div>

    
<div class="iso__container-iso">

  {#each years as year, index}
    <div class="row">
      <div class="side left-side">
        <p class="numbers-left">{numbers[index]} mil</p>
                <div class="isotype-left">
          {#each Array(numbers[index]) as m}
            <div class="face-wrapper" style="--circle-opacity: {opacityScale(numbers[index])}">
              <img
                class="face"
                src={getRandomImage1()}
                alt="cara"
              />
            </div>
          {/each}
        </div>
      </div>
      
      <div class="year-label-container">
        <div class="year-label">{year}</div>
      </div>
      
      <div class="side right-side">
        <div class="isotype-right">
          {#each Array(numbers2[index]) as m}
          <div class="face-wrapper2" style="--circle-opacity: {opacityScale2(numbers2[index])}">
              <img
                class="face"
                src={getRandomImage2()} 
                alt="cara invierno"
              />
            </div>
          {/each}
        </div>
        <p class="numbers-right">{numbers2[index]} mil</p>
            </div>
    </div>

<!--<p class="info-textos">textos</p>-->
<!-- Añadir párrafos entre los años específicos -->
{#if year === 2016}
<p class="info-text">
  En 2017, los destinos de veraneo parecían alcanzar el nivel de popularidad de los destinos invernales. Las estaciones de esquí estaban llenas de esquiadores, mientras que las playas estaban abarrotadas de turistas. Sin embargo, poco a poco, se empezaba a notar que había cada vez menos nieve.
</p>
{/if}

{#if year === 2019}
<p class="info-text">
  Con el paso de los años, la tendencia se hizo más evidente. En 2023, los destinos de verano alcanzaron casi el 100% de popularidad, mientras que los invernales se estancaron en cifras mucho más bajas. La falta de nieve en algunas regiones y el cambio en las preferencias de los viajeros llevaron a una disminución en las visitas a estaciones de esquí. Las familias buscaban experiencias más cálidas y emocionantes, y las agencias de viajes se dieron cuenta de que debían adaptarse.
</p>
{/if}

{#if year === 2021}
<p class="info-text">
  Frente a esta transformación, las empresas de turismo de los destinos invernales comenzaron a replantearse sus estrategias. Las estaciones de esquí, por ejemplo, empezaron a diversificar sus ofertas, creando actividades como senderismo y ciclismo de montaña. A pesar de ello, la cantidad de turistas que visitaban los destinos invernales continuaba disminuyendo.
</p>
{/if}

{#if year === 2023}
<p class="info-text">
  Con el tiempo, la industria turística aprendió a adaptarse a las nuevas preferencias de los viajeros. Sin embargo, los destinos invernales nunca lograron volver a ser lo que eran debido a la falta de nieve. Por su parte, los destinos de verano continuaron prosperando.
</p>
{/if}

{/each}
</div>



<main>
  <main>
    <div class="chart-container">
      <div class="chart-wrapper">
        
        <iframe src='https://flo.uri.sh/visualisation/19289560/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'>
        </div>
        
        <div class="chart-wrapper">
          <iframe src='https://flo.uri.sh/visualisation/19355491/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:100%;height:600px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'>
          </iframe>
        </div>
   
  
      <div class="chart-wrapper">
        <div class="flourish-embed flourish-chart" data-src="visualisation/19355491"><script src="https://public.flourish.studio/resources/embed.js"></script><noscript><img src="https://public.flourish.studio/visualisation/19355491/thumbnail" width="100%" alt="chart visualization" /></noscript></div>      </div>
      <div class="chart-wrapper full-width">
        <iframe src='https://flo.uri.sh/visualisation/19356462/embed' title='Interactive or visual content' class='flourish-embed-iframe' frameborder='0' scrolling='no' style='width:104%;height:400px;' sandbox='allow-same-origin allow-forms allow-scripts allow-downloads allow-popups allow-popups-to-escape-sandbox allow-top-navigation-by-user-activation'></iframe><div style='width:100%!;margin-top:4px!important;text-align:right!important;'><a class='flourish-credit' href='https://public.flourish.studio/visualisation/19356462/?utm_source=embed&utm_campaign=visualisation/19356462' target='_top' style='text-decoration:none!important'><img alt='Made with Flourish' src='https://public.flourish.studio/resources/made_with_flourish.svg' style='width:105px!important;height:16px!important;border:none!important;margin:0!important;'> </a></div>            
      </div>
    </div>
</main>

  <!-- Contenedor de los números -->
  <div class="grid-container">
    <div class="grid-item">
      <h2>{totalVisitantes}</h2>
      <p>visitantes totales</p>
    </div>
  
    <div class="grid-item orange">
      <h2>{visitantesVerano}</h2>
      <p>visitantes de veraneo</p>
    </div>
  
    <div class="grid-item blue">
      <h2>{visitantesInvierno}</h2>
      <p>visitantes invernales</p>
    </div>
  </div>

  <!-- Botón para desplazarse hacia arriba -->
<div class="scroll-to-top">
  <button on:click={scrollToTop} class="scroll-button">
    ▲
  </button>
  
</div>

<footer class="footer">
  <p>FÁTIMA PAULUK & ZOE GASPAR</p>
  <div class="footer-direccion">
    <p>@paulukfatimalab  @labdezoe</p>
    
  </div>
</footer>

</main>



<style>

  @import url('https://fonts.googleapis.com/css2?family=Open+Sans:ital,wght@0,300..800;1,300..800&display=swap');

  :global(body) {
  font-family: 'Open Sans', sans-serif; 
  }
  
  h1.titulo {
    text-align: center;
    font-size: 120px;
    font-weight: bold;
    margin-top: 60px; /* Espacio arriba del título */
    margin-bottom: 60px; /* Espacio abajo del título */
  }

  h2.subtitulo {
    text-align: center;
    font-size: 28px;
    margin: 0 auto;
    max-width: 800px;
    line-height: 1.4;
    margin-bottom: 100px; /* Espacio abajo del subtítulo */
  }

  .rectangulo, .info-text {
    max-width: 900px;
    margin: 20px auto;
    padding: 20px;
    border: 2px solid #000;
    background-color: white;
    border-radius: 10px;
    font-size: 20px;
    line-height: 1.5;
    text-align: center;
    position: relative; /* Necesario para aplicar z-index */
    z-index: 3;
    margin-bottom: 40px; /* Espacio abajo del rectángulo */
    margin-top: 100px;
  }

 
  h3 {
    text-align: center;
    font-size: 40px;
    font-weight: bold;
    margin-top: 20px;
    margin-bottom: 20px;
  
  }
  .iso__container-iso {
    display: flex;
    flex-direction: column;
    max-width: 100%;
    align-items: center;
    justify-content: space-between;
    position: relative; /* metodo de posicionamiento en la pagina html*/
  }

  .iso__container-iso::before { /* el before crea como un hijo del contenedor principal*/
    content: '';
    position: absolute; /* toma la posicion del padre*/
    top: 0;
    bottom: 0;
    left: 50%;
    width: 2px; /* grosor linea*/
    background-color: #000;
    transform: translateX(-50%); /* para centrar la linea*/
    z-index: 1; /* hace que las lineas esten atras del año*/
  }
  .row {
    display: flex;
    align-items: center;
    justify-content: space-between;
    margin-bottom: 50px;
    margin-top: 50px;
    width: 100%;
     align-items: flex-start; /* Alinea los elementos al inicio */
}
  

  .side {
    display: flex;
    align-items: center;
    width: 40%; /* Reducido ligeramente para dar más espacio al año */
    align-items: flex-start; /* Alinea los elementos al inicio */
  
  }

  .left-side {
    justify-content: flex-end;
    padding-right: 20px;
    font-weight: 600;
  }

  .right-side {
    justify-content: flex-start;
    padding-left: 50px;
    font-weight: 600;
  }

  .isotype-left, .isotype-right {
    display: flex;
    flex-wrap: wrap;
    width: 80%;
    align-items: flex-start; /* Alinea los elementos al inicio */
  
  }

  .year-label-container {
    position: relative;
    width: 20%;
    display: flex;
    justify-content: center;
    align-self: flex-start; /* Alinea el año al inicio */
  padding-top: 10px; /* Ajusta este valor para alinear el año con los números */
  }

  .year-label {
    background-color: white;
    padding: 5px 10px;
    font-weight: bold;
    font-size: 50px;
    z-index: 2;
    position: relative;
  }
  .numbers-left, .numbers-right {
    font-size: 50px;
    width: 110px;
    text-align: center;
    margin-left:  20px;
    margin-right:  20px;
    align-items: flex-start; /* Alinea los elementos al inicio */
  
  }

  .numbers-left {
    color: #F99F1D;
  }

  .numbers-right {
    color: #53C8F4;
  }

  .face-wrapper, .face-wrapper2 {
    position: relative;
    display: inline-block;
    margin: 4px;
  }

  .face {
    height: 70px;
    width: 70px;
    position: relative;
    z-index: 1;
  }

  .face-wrapper::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    z-index: 0;
    opacity: var(--circle-opacity);
    background-color: #F99F1D;
  }


  .face-wrapper2::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    width: 70px;
    height: 70px;
    border-radius: 50%;
    z-index: 0;
    opacity: var(--circle-opacity);
    background-color: #53C8F4;
  }

  .info-text {
    font-size: 18px;
    margin: 20px 0;
    text-align: justify;
    max-width: 800px;
    line-height: 1.5;
  }

  .chart-container {
  display: grid;
  grid-template-columns: 1fr 1fr; /* Dos columnas iguales */
  gap: 20px; /* Espacio entre los gráficos */
  max-width: 2000px; /* Ancho máximo del contenedor */
  margin: 0 auto; /* Centrar el contenedor */
  padding: 40px; /* Espacio alrededor */
}

.chart-wrapper {
  background-color: white; /* Fondo blanco para los gráficos */
  border-radius: 10px; /* Bordes redondeados */
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); /* Sombra para dar un efecto flotante */
  padding: 20px; /* Espacio interno alrededor del gráfico */
}

/* El gráfico en la segunda fila ocupará el ancho completo */
.full-width {
  grid-column: span 2;
}


  .grid-container {
    display: flex;
    justify-content: center;
    text-align: center;
    gap: 400px;
    margin-top: 30px;
    margin-bottom: 150px;
  }

  .grid-item h2 {
    font-size: 120px;
    margin: 0;
    color: black;
  }

  .grid-item p {
    font-size: 24px;
    margin-top: 10px;
  }

  .orange {
    color: #f98b1c;
  }

  .blue {
    color: #51c5f6;
  }

/* Botón para desplazarse hacia arriba */
.scroll-to-top {
  display: flex;
  justify-content: center;
  margin-top: 50px; /* Espacio arriba del botón */
  margin-bottom: 100px; /* Espacio abajo del botón */
}

.scroll-button {
  background-color: white; /* Fondo blanco */
  border: 2px solid black; /* Trazo negro */
  border-radius: 50%; /* Botón redondo */
  width: 60px; /* Ancho del botón */
  height: 60px; /* Alto del botón */
  font-size: 24px; /* Tamaño de la flecha */
  color: black; /* Color de la flecha */
  cursor: pointer; /* Cambia el cursor al pasar sobre el botón */
  display: flex;
  align-items: center;
  justify-content: center;
  transition: background-color 0.3s, transform 0.3s; /* Transiciones para hover */
}

.scroll-button:hover {
  background-color: #f98b1c; 
  transform: scale(1.1); 
}

.footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 40px;
  background-color: #000;
  color: #fff;
  font-size: 18px;
  font-weight: bold;
  text-transform: uppercase;
  width: 100%;
}

.footer-direccion {
  display: flex;
  
}


.escala {
  display: flex;           
  justify-content: center;  
  align-items: center;      
 
}

.titulos {
  display: flex;
  justify-content: space-between;
  align-items: center;
  max-width: 80%;
  margin: 0 auto 40px;
  padding: 0 20px;
}

</style>