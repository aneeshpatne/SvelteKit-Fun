<script>
    import {onMount} from 'svelte';
    let Theme = true;
    let Mounted = false;
    function updateBodyClass(){
        if (Mounted){
        document.body.classList.remove(Theme ? 'light' : 'dark');
        document.body.classList.add(Theme ? 'dark' : 'light');
    }};
    function themeToggle(){
        Theme =! Theme;
        localStorage.setItem('theme', Theme ? 'dark' : ' light');
        updateBodyClass();
    }
    onMount(()=>{
        Mounted  = true;
        const prevTheme = localStorage.getItem('theme');
        Theme = prevTheme ==='dark'; 
        updateBodyClass();
        });

    
</script>
{Theme}
<button on:click={() => themeToggle()}>Click Me</button>