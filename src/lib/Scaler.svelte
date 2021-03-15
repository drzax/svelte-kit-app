<script lang="ts">
  import { scaleLinear } from 'd3-scale';
  let rangeMin: number = 0;
  let rangeMax: number = 1;
  let domainMin: number = 0;
  let domainMax: number = 100;
  let inputValue: number = 50;

  $: scale = scaleLinear()
    .domain([domainMin, domainMax])
    .range([rangeMin, rangeMax]);
  $: value = scale(inputValue);
</script>

<h2>Range</h2>
<input
  type="range"
  min="0"
  max="1"
  step="0.1"
  bind:value={rangeMin}
/>{rangeMin}
<input
  type="range"
  min="0"
  max="1"
  step="0.1"
  bind:value={rangeMax}
/>{rangeMax}
<h2>Domain</h2>
<input type="range" min="0" max="100" bind:value={domainMin} />{domainMin}
<input type="range" min="0" max="100" bind:value={domainMax} />{domainMax}

<h2>Input</h2>
<input type="range" min="0" max="100" bind:value={inputValue} />

<p><strong>Input: </strong> {inputValue}</p>
<p><strong>Scaled: </strong> {value}</p>

<style lang="scss">
  input[type='range'] {
    width: 40%;
    margin: 0 auto;
  }
</style>
