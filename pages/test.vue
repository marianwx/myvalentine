<template>
    <img src="https://cdn-icons-png.flaticon.com/128/508/508786.png" id="heartbeat">
    
  </template>
  
  <style>
  /* Include the keyframes and animation in the style block */
  @keyframes heartbeat {
    0% {
      transform: scale(1);
    }
    25% {
      transform: scale(1.1);
    }
    50% {
      transform: scale(1);
    }
    75% {
      transform: scale(0.9);
    }
    100% {
      transform: scale(1);
    }
  }
  
  #heartbeat {
    animation: heartbeat 0.6s ease-out infinite;
  }
  </style>
  