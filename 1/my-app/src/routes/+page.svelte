<style>
    :global(.dark-mode){
        background-color: rgb(55, 54, 59);
        color: rgb(255, 255, 255);
    }
    #green-text{
        color: rgb(75, 117, 54);

    }
    #box{
        width: 100px;
        height: 100px;
    }
    .red{
        background-color: rgb(236, 158, 158);
    }
    .blue{
        background-color: rgb(102, 242, 177);
    }

    </style>
<script>
import {onMount} from 'svelte';
let variable = 7;
let var1 = true;
function classSetter(){
    if (typeof window !== 'undefined'){
    if (var1){
        document.body.classList.add('dark-mode');
        localStorage.setItem('theme', 'true');
    }
    else{
        document.body.classList.remove('dark-mode');
        localStorage.setItem('theme', 'false');

    }
}
};
onMount(()=>{
const prevValue =localStorage.getItem('theme');
if (prevValue !== null){
    var1 = prevValue === 'true';
}
classSetter();
});
$: var1, classSetter();
</script>



<h1 id="green-text">Hello!</h1>
<button on:click={()=>variable++}>Click Me</button>
{variable}
<div id="box" class={var1 === true ? 'red' : 'blue'}></div>
<button on:click={() => var1 = !var1}> Toggle</button>
{var1}