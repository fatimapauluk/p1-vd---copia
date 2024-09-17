<!-- Script JS -->
<script>
  import * as d3 from "d3"
  import IsotypeBars from "./lib/Caras.svelte"

let numbers = [21, 33, 42, 54, 63, 71, 77, 84, 92, 98]
let numbers2 = [23, 35, 45, 56, 50, 43, 38, 32, 28, 25]
let years = [2014,2015,2016,2017,2018,2019,2020,2021,2022,2023];


function altura(n) {
    let scale = d3
      .scaleLinear()
      .domain([0, 100]) // [mínimo, máximo]
      .range([0, 225]) // [altura_minima, altura_máxima]
    return scale(n)
  }

  

</script>



<main>

  <IsotypeBars
  numbers={numbers}
  numbers2={numbers2}
  years={years} 
/>
<hr />
<!-- Barras Isotipos 
<IsotypeBars
numbers={numbers}
years={years} 
/>
<hr />

<IsotypeBars
numbers={numbers2}
years={years} 
title="Cara a cara con los datos"
/>
<hr />
 -->

</main>


<style>
:global(.flourish-credit) {
  display: none;
}



</style>
