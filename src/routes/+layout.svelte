<nav>
    <div class="nav-container">
      <a href="/" class="nav-logo" title="Back to Homepage">Имя 
        Фамилия</a>
         <div class="nav-links">
             {#each nav as link}
                <a href = {link.href} class="link">{link.title}</a>
             {/each}
         </div>
    </div>
</nav>

<div class="container">
    <!-- Pages will be injected below --> 
    <slot></slot>
</div>

<script>
  import { each,  } from "svelte/internal";

    const nav = [
        {
            title : "About me",
            href : "/about"
        },
        {
            title : "Blog",
            href : "/blog"
        },
        {
            title : "Portfolio",
            href : "/project"
        },
        {
            title : "Contacts",
            href : "/contact"
        },
        {
            title : "Temp",
            href : "/temp"
        }
    ]
</script>


<style>
    .container {
    max-width: 1400px; margin: 50px auto;
    }
</style>