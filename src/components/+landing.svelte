<script>
    export let appName;
    export let appDescription;
    import { goto } from "$app/navigation";
    const handleClick = () => {
      goto('/test_app')
    }
</script>
<div class="my-11 mx-10">
    <h1 class="text-3xl">
       {appName}:
    </h1>
    <br />
    <h4 class="text-xl">
       {appDescription}
    </h4>
 </div>
 
 <div class="flex">
    <button 
        class="flex-none bg-gray-200 hover:bg-gray-700 text-black hover:text-white font-bold w-44 h-32 mx-10 rounded" 
        on:click="{handleClick}"    
    >
       Test App 1
    </button>
    <button class="flex-initial bg-gray-200 hover:bg-gray-700 text-black hover:text-white font-bold w-44 h-32 mx-10 rounded">
       Test App 2
    </button>
    <button class="flex-initial bg-gray-200 hover:bg-gray-700 text-black hover:text-white font-bold w-44 h-32 mx-10 rounded">
       Test App 3
    </button>
 </div>