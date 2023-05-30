<nav>
    <div class="nav-container">
      <a href="/" class="nav-logo" title="Back to Homepage">Имя 
        Фамилия</a>
         <div class="nav-links">
             {#each nav as link}
               {#if link.isShow}
                  <a href = {link.href} class="link">{link.title}</a>
               {/if}
                
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
            href : "/about",
            isShow : true
        },
        {
            title : "Blog",
            href : "/blog",
            isShow : true
        },
        {
            title : "Portfolio",
            href : "/project",
            isShow : true
        },
        {
            title : "Contacts",
            href : "/contact",
            isShow : true
        },
        {
            title : "Temp",
            href : "/temp",
            isShow : false
        }
    ]
</script>


<style>
    .container {
    max-width: 1400px; margin: 50px auto;
    }
</style>