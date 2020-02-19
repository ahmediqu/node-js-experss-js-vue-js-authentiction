<template>
<nav class="navbar navbar-expand-lg navbar-light bg-light">
    <div class="container">
  <router-link  class="navbar-brand" :to="{ name: 'HelloWorld'}"> { Full Stack App }</router-link>
  <button class="navbar-toggler" type="button" data-toggle="collapse" data-target="#navbarNavAltMarkup" aria-controls="navbarNavAltMarkup" aria-expanded="false" aria-label="Toggle navigation">
    <span class="navbar-toggler-icon"></span>
  </button>
  <div class="collapse navbar-collapse" id="navbarSupportedContent">
    <ul class="navbar-nav ml-auto">
      
      <li class="nav-item">
        <router-link class="nav-link" active-class="active" :to="{ name: 'signin'}" >Sign In</router-link>
      </li>
      <li class="nav-item">
        <router-link class="nav-link" active-class="active" :to="{ name: 'signup'}" >Sign Up</router-link>
      </li>
    </ul>
  </div>
  </div>
</nav>
</template>