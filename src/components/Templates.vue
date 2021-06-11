<template>
  <div class="templates__container">
   <h6>Partie bientôt disponible</h6>
       <button class="starting__button" @click.prevent="$emit('openNav')">
      <p>Continuer la visite</p>
      <svg
        version="1.0"
        xmlns="http://www.w3.org/2000/svg"
        width="25px"
        height="20px"
        viewBox="0 0 1280.000000 640.000000"
        preserveAspectRatio="xMidYMid meet"
      >
        <metadata>
          Created by potrace 1.15, written by Peter Selinger 2001-2017
        </metadata>
        <g
          transform="translate(0.000000,640.000000) scale(0.100000,-0.100000)"
          fill="#000000"
          stroke="none"
        >
          <path
          fill="#FFC108"
            d="M9280 5934 c-106 -21 -223 -80 -293 -150 -99 -97 -148 -196 -168
            -336 -10 -72 -9 -97 5 -164 22 -108 75 -212 144 -282 33 -33 391 -297 851
            -627 l794 -570 -5084 -5 c-4763 -5 -5087 -6 -5132 -22 -146 -52 -265 -152
            -330 -275 -114 -217 -77 -472 93 -644 70 -71 126 -108 217 -142 l58 -22 5078
            -5 5078 -5 -752 -615 c-414 -338 -776 -638 -804 -667 -29 -29 -68 -84 -89
            -125 -112 -224 -73 -470 105 -649 104 -105 233 -159 382 -159 99 0 186 22 270
            68 70 39 2847 2303 2942 2399 160 162 199 422 93 633 -46 94 -119 163 -324
            311 -1086 782 -2701 1940 -2747 1970 -83 54 -166 80 -272 84 -49 2 -101 1
            -115 -1z"
          />
        </g>
      </svg>
    </button>
  </div>
</template>

<script>
export default {
  name: 'Templates'
}
</script>

<style  lang="scss" scoped>

@import '../styles/_variables.scss';

.templates__container {
  height: 100%;
  width: 100%;
  padding: 150px 0;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;

  h6 {
    font-size: 3rem;
  }
}

.starting__button {
    cursor: pointer;
    position: relative;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 50px;
    width: 250px;
    border-radius: 2px;
    border: none;
    background: $yellow;
    font-size: 1rem;
    transition: all 0.4s;

    &:after {
        content: '';
        position: absolute;
        right: -40px;
        width: 40px;
        height: 40px;
        transform: rotate(45deg) translateX(-100px) translateY(100px);
        border: 2px solid $yellow;
        opacity: 0;
        transition: all 0.4s;
    }

    svg {
      position: absolute;
      right: -30px;
      transform: translateX(-100px);
      opacity: 0;
      transition: all 0.4s;
    }

    &:hover {
        width: 230px;
        background: transparent;
        border: 2px solid $yellow;
        color: $yellow;

        &:after {
            right: -40px;
            transform: rotate(45deg) translateX(0);
            opacity: 1;
        }

        svg {
            transform: translateX(0);
            opacity: 1;
        }
    }
  }

</style>