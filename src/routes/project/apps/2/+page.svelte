<script>
    let newItem = "";
    let newAmount = "";
    let expenseList = [];
    let sum = "";

    function add () {
        if (newItem !== "" && newAmount !== ""){
            expenseList = [
                ...expenseList,
                {
                    Name: newItem,
                    Amount: parseInt(newAmount),
                    
                }
            ]
            newItem = "";
            newAmount = "";
        }
    }

    function deleteExpense (index){
        expenseList.splice(index, 1);
        expenseList = expenseList;
        sum = "";
    }

    function calcSum (){
        let amounts = expenseList.map((item) => item.Amount);
        sum = parseInt(amounts.reduce(
            (accumulator, currentValue) => accumulator + currentValue,
        ));


    }

    //  calcSum ();

        

    //     let sum = amounts.reduce(
    //       (accumulator, currentValue) => accumulator + currentValue,
    //     );
    // }
    

    // let amountSum = expenseList.reduce(function(sum) {
	    
        
        
    //     return sum + expenseList.newAmount;
    //  }, 0
    // );


</script>

<main>
    <h1>Учет расходов</h1>
    <form on:submit|preventDefault={add}>
       
        <input bind:value={newItem} placeholder="Введите название">
       <input bind:value={newAmount} placeholder="Введите сумму">
       <button class="add-Item" on:click={add} on:click={() => calcSum ()}><span>Добавить</span></button>
    </form>
    

    <table>
        <thead>
            <tr>
                <th>Название</th>
                <th>Сумма</th>
                <th>Действия</th>
            </tr>
        </thead>
        <tbody>
            {#each expenseList as item, i }
            <tr>
                <td><div>{item.Name}</div></td>
                <td><div>{item.Amount}</div></td>
                <td><button class="delete" on:click={() => deleteExpense (i)}  on:click={() => calcSum ()}>Удалить</button></td>
            </tr>
            {/each}
            <tr class="totalAmount">
                <td><div >Общая сумма</div></td>
                
                <td><div>{sum}</div></td>
            </tr> 
        </tbody>
    </table>
        
</main>
        
        
        
<style>
    main{
        display: flex;
        flex-direction: column;
        align-items: center;
        min-height: 100%;
        padding: 5vmin;
        box-sizing: border-box;
        background: rgb(160, 173, 184);
        border-radius: 15px;
    }
    form{
        width: 100%;
        max-width: 500px;
        display: flex;
        align-items: center;
        margin-bottom: 1rem ;
    }

    input{
        flex-grow: 1;
        width: 0;
        border: none;
        border-bottom: 1px solid black;
        box-shadow: none;
        font-size: 1.2rem;
        margin: 10px;
        outline: none;
    }

    table, th, td {
      border: 1px solid black;
    }

    table{
        width: 100%;
        border-collapse: collapse;
        background-color: rgb(233, 242, 249);

        
        
    }

    th, td {
    padding: 15px;
    text-align: left;
}

button { 
    background-color: rgba(25, 167, 25, 0.518);;
    width: 92px;
    padding: 4px;
    margin: 0;
    flex-shrink: 0;
    border-radius: 10px;

    
}

.delete{
    background-color: rgba(165, 42, 42, 0.482);
}

.totalAmount{
    background-color: rgba(25, 167, 25, 0.518);
}


</style>








