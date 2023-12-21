<template>
    <div class="footer">
      <p>Current Random Fact: {{ fact }}</p>
    </div>
  </template>
  
  <script setup>
  import { defineProps } from 'vue'
  
  const props = defineProps({
    fact: {}
  })
  </script>
  
  <style>
  .footer {
    position: fixed;
    bottom: 0;
    left: 0;
    width: 100%;
    background-color: #000;
    padding: 10px;
  }
  </style>
  