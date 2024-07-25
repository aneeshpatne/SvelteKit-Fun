<script>
    import {onMount} from 'svelte';
    let Theme;
    function themeToggle(){
        Theme =! Theme;
        localStorage.setItem('theme', Theme);
    }
    onMount(()=>{
        let var1 = localStorage.getItem('theme');
        console.log(var1);
        Theme = var1 ? var1 : true ; 
        });
</script>
{Theme}
<button on:click={() => themeToggle()}>Click Me</button>