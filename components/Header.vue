<template>
  <div class="header">
    <div class="logo">
      <nuxt-link to="/">
        <svg width="36" height="36" viewBox="0 0 36 36" fill="none" xmlns="http://www.w3.org/2000/svg">
          <path d="M1 4C1 2.34314 2.34314 1 4 1H32C33.6569 1 35 2.34315 35 4V14.9C35 16.5569 33.6569 17.9 32 17.9H4C2.34315 17.9 1 16.5569 1 14.9V4Z" stroke="#5AC0ED" stroke-width="2" />
          <path d="M14 1C15.6569 1 17 2.34315 17 4L17 32C17 33.6569 15.6569 35 14 35L4 35C2.34315 35 1 33.6569 1 32L1 4C1 2.34314 2.34315 0.999999 4 0.999999L14 1Z" stroke="#5AC0ED" stroke-width="2" />
        </svg>
      </nuxt-link>
    </div>
    <nav class="nav">
      <a href="https://github.com/osuke" target="_blank">Github</a>
      <a href="https://twitter.com/__osuke" target="_blank">Twitter</a>
      <a href="https://docs.google.com/forms/d/1iwWE_kyJeR57F4MvIKWqdYfdrPZMabTTPAlO24gJNpM/edit" target="_blank">Contact</a>
    </nav>
  </div>
</template>
<style>
.header {
  padding: 16px 0;
  margin-bottom: 25px;
  display: flex;
  justify-content: space-between;
}

.nav {
  margin-top: 8px;
}

.nav a {
  color: #555;
  text-decoration: none;
  margin-left: 24px;
  font-size: 14px;
}
</style>
