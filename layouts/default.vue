<template>
  <div>
    <nav class="navbar">
        <NuxtLink to="/">
            Home
        </NuxtLink>
        <NuxtLink to="/github">
            Repos
        </NuxtLink>
    </nav>
    <slot />
    <footer class="footer">
        Footer I guess
    </footer>
  </div>
</template>