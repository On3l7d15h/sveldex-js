<script>
    export let idpkmn = 1;

    const getData = () => {
        Swal.fire({
            title: "Indique el id!",
            input: "text",
            inputAttribute: {
                autocapitalize: "off"
            },
            icon: "question",
            showCancelButton: true,
            confirmButtonText: "buscar"
        })
        .then((result) => {
            if(result.isConfirmed && result.value < 899){
               idpkmn = parseInt(result.value) 
            } 
            else if(result.isDismissed){
                
            } 
            else{
                Swal.fire({
                    title: "Oops!",
                    text: "Solo existen Pokemones de ID 898 para abajo!",
                    icon: "error"
                })
            }  
        })

    }
</script>

<section class="container-search"> 
    <h1> Aquí tu busqueda del pokemón!!</h1>
    <form on:submit|preventDefault>
        <label>
            Id Pokemón: 
            <input disabled type="text" bind:value={idpkmn} />
            <button on:click={getData}>
                Insertar Id
            </button>
        </label>
    </form>
</section>

<style>

    .container-search
    {
        max-width: calc(100% - 40%);
        background: var(--c-white);
        width: 100%;
        padding: 10px;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: center;
        align-items: center;
        border-radius: 5px;
        box-shadow: 0 2px 8px 0 var(--c-black-trans);
        backdrop-filter: blur(10px);
        border-top: 2px solid var(--c-tomato-cake);
        border-left: 2px solid var(--c-tomato-cake);
        position: relative;
        top: -50px;
    }

        .container-search h1
        {
            font-size: 35px;
            margin: 10px auto;
        }

        .container-search form
        {
            width: 80%;
            padding: 5px;
            display: flex;
            flex-direction: row;
            flex-wrap: nowrap;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .container-search form label
        {
            margin: 10px auto;
            padding: 5px;
            font-weight: bold;
            font-size: 18px;
        }

            .container-search form label input
            {
                width: 30%;
                outline: 0;
                padding: 5px;
                border-radius: 5px;
                border: 1px solid var(--c-tomato);
                color: var(--c-tomato);
                font-weight: bold;
                text-align: center;
            }

                .container-search form label input:disabled
                {
                    background: var(--c-white);
                    color: var(--c-tomato);
                }

                .container-search form label button
                {
                    background: var(--c-tomato);
                    color: var(--c-white);
                    font-weight: bold;
                    border-radius: 5px;
                    font-size: 18px;
                    border: 0;
                    padding: 5px;
                    cursor: pointer;
                }

</style>