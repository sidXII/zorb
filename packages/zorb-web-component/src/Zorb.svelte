<svelte:options tag="zora-zorb" accessors={true} immutable={false} />

<script lang="ts">
  import { gradientForAddress } from "./lib";
  import {instanceCount} from './instanceCounter';
  export let size = '100%';
  export let address = "0x0000000000000000000000000000000000000000";
  
  const gradientInfo = gradientForAddress(address);
</script>

<svg width={size} height={size} xmlns="http://www.w3.org/2000/svg" viewBox="0 0 110 110">
  <defs>
    <radialGradient
      id={`gzr${instanceCount}`}
      gradientTransform="translate(66.4578 24.3575) scale(75.2908)"
      gradientUnits="userSpaceOnUse"
      r="1"
      cx="0"
      cy="0%"
      >
      <stop offset="15.62%" stop-color={gradientInfo[0]} />
      <stop offset="39.58%" stop-color={gradientInfo[1]} />
      <stop offset="72.92%" stop-color={gradientInfo[2]} />
      <stop offset="90.63%" stop-color={gradientInfo[3]} />
      <stop offset="100%" stop-color={gradientInfo[4]} />
    </radialGradient>
  </defs>
  <g transform="translate(5,5)">
    <path
      d="M100 50C100 22.3858 77.6142 0 50 0C22.3858 0 0 22.3858 0 50C0 77.6142 22.3858 100 50 100C77.6142 100 100 77.6142 100 50Z"
      fill={`url(#gzr${instanceCount})`}
    /><path
      stroke="rgba(0,0,0,0.075)"
      fill="transparent"
      stroke-width="1"
      d="M50,0.5c27.3,0,49.5,22.2,49.5,49.5S77.3,99.5,50,99.5S0.5,77.3,0.5,50S22.7,0.5,50,0.5z"
    />
  </g>
</svg>
