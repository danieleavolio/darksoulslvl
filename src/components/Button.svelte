<script lang="ts">
    export let content:string ="";


</script>


<button on:click>{content}</button>


<style>

*{
	font-family: 'Cormorant', serif;
}    
    button{
        border:none;
        outline:none;
        padding: 1rem;
        background-color: #F6C90E;
        margin:3rem;
		font-weight: 700;
        font-size: 2rem;
        cursor: pointer;
        border-radius: 4px;
        font-weight: 600;
    }
</style>