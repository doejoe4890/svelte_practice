<script>
    export let tableData;
    let limit = 10;
    let numRows = tableData.length
    $: numPages = Math.ceil(numRows/ limit);
    console.log(numPages)
</script>

<div>
  <table class="table-auto border">
    <thead>
      <tr>
        {#each Object.keys(tableData[0]) as columnHeading}
          <th class="font-bold py-2 px-4 border-b border-l text-left">{columnHeading}</th>
        {/each}
      <tr/>
    </thead>

    <tbody>
      {#each Object.values(tableData) as row}
        <tr class="odd:bg-gray-100 hover:bg-stone-100">
          {#each Object.values(row) as cell}
            <td class="p-2 border-b border-l text-left">{cell}</td>
          {/each}
        </tr>
      {/each}
    </tbody>
  </table>
</div>  

<style>
  table, th, td {
    border: 1px solid;
    border-collapse: collapse;
    margin: 10px;
  }
</style>