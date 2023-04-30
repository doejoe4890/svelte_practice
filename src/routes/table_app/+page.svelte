<script>
    import GridCtrl from '../../components/gridCtrl.svelte';
    import { testData } from '../../data/data-store';
    let val = '';
</script>

<div>
    <p class="text-2xl m-8"> Page Title</p>
</div>
<div class="flex flex-row border mt-2">
    <div class="basis-1/4 ml-8 mt-4">
        <p class="text-xl">Table Title</p>
    </div>
    <div class="basis-1/3">
    
    </div>
    <div class="basis-2/3">
    
    </div>
    <div class="basis-1/3 mt-4 mb-4">
        <input bind:value={val} type="text" id="searchInput" placeholder="Enter Text Here To Search">
        <button 
            class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" 
        >
        Refresh
        </button>
    </div>
</div>

<GridCtrl tableData={$testData}/>