<script>
let variable = 7;

</script>
<style>
#green-text{
    color: rgb(75, 117, 54);
}
</style>
<h1 id="green-text">Hello!</h1>
<button on:click={()=>variable++}>Click Me</button>
{variable}