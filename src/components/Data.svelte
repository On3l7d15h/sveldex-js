<script>
    export let idpk;

    $: info = {}

    // funciones
    $: getDataApi = async (id) => {
        // haciendo fetch a la Api
        await fetch(`https://pokeapi.co/api/v2/pokemon/${id}`)
                .then((res) => res.json())
                .then((data) => { 
                    info = data; 
                    console.log(data)
                    return data
                })
                .catch((err) => console.log(err))
    }

    $: if(idpk !== 0 && idpk !== ""){
        getDataApi(idpk) 
    } 

</script>

<div class="container-data">
    {#if idpk !== 0 && idpk !== ""}
        <section class="container-data-img">
            <img src={(info.sprites) ? info.sprites.front_default : ""} alt="..." />
            <img src={(info.sprites) ? info.sprites.back_default : ""} alt="..." />
        </section>
        <section class="container-data-info">
            <h1>Aquí tus datos</h1>
            <table>
                <thead>
                    <td>ID:</td>
                    <td>Nombre:</td>
                    <td>Tipos:</td>
                    <td>Habilidades</td>
                </thead>
                <tr>
                    <td>{info.id}</td>
                    <td><img src="images/descarga2.png" alt="..." /></td>
                    <td>
                        {(info.types) ? info.types[0].type.name : ""}
                        {(info.types && info.types[1] !== undefined) ? ` - ${ info.types[1].type.name }` : ""}
                    </td>
                    <td>
                        <img src="images/descarga2.png" alt="..." />
                    </td>
                </tr>
                <tr>
                    <td><img src="images/descarga2.png" alt="..." /></td>
                    <td>{info.name}</td>
                    <td>
                        <img src="images/descarga2.png" alt="..." />
                    </td>
                    <td>
                        {(info.abilities) ? info.abilities[0].ability.name : ""} 
                        {(info.abilities && info.abilities[1 !== undefined]) ? `- ${ info.abilities[1].ability.name }` : ""}
                    </td>
                </tr>
            </table>
        </section>
    {:else}
        <h1>Nada por mostrar</h1>
    {/if}
</div>

<style>
    /* your styles go here */
    .container-data
    {
        width: 80%;
        background: var(--c-white);
        padding: 5px;
        display: flex; 
        flex-direction: row;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        padding: 10px;
        box-shadow: 0 2px 8px 0 var(--c-black-trans);
        border-radius: 5px;
    }

        .container-data .container-data-img
        {
            width: 100%;
            max-width: 20%;
            margin: 5px 15px;
            border-radius: 5px;
            overflow: hidden;
            box-shadow: 0 4px 8px 0 var(--c-black-trans);
            overflow: hidden;
        }

            .container-data-img img 
            {
                width: 100%;
                transition: .5s all ease;
            }

                .container-data-img img:hover 
                {
                    background: var(--c-tomato-cake);
                    transform: scale(1.1)
                }

        .container-data .container-data-info
        {
            width: 100%;
            max-width: 67%;
            padding: 5px;
            margin: 0 10px;
            border-radius: 5px;
            background: var(--c-tomato-cake);
            color: var(--c-white);
            line-height: 2;
            box-shadow: 0 2px 8px 0 var(--c-black-trans);
            display: flex;
            flex-direction: row;
            flex-wrap: wrap;
        }

            .container-data-info h1 
            {
                align-items: center;
                margin: 0 auto;
                font-size: 36px;
            }

            .container-data-info table 
            {
                width: 100%;
            }

            .container-data-info table thead
            {
                padding: 5px;
                font-weight: bold;
                font-size: 20px;
                width: 100%;
            }

                .container-data-info table thead td
                {
                    background: var(--c-tomato-cake);
                    color: var(--c-white);
                    text-align: center;
                }

                .container-data-info table tr
                {
                    width: 100%;
                }

                    .container-data-info table tr td
                    {
                        max-width: calc(100% - 75%);
                        width: 100%;
                        font-size: 20px;
                        font-weight: bold;
                        text-align: center;
                        background: var(--c-white);
                        color: var(--c-tomato-cake);
                        transition: .5s all ease;
                    }

                        .container-data-info table tr td:hover
                        {
                            background: var(--c-tomato-cake);
                            color: var(--c-white);
                            transform: scale(0.9);
                            overflow: hidden;
                        }

                    .container-data-info table tr td img
                    {
                        width: 60%;
                        text-align: center;
                        transition: .5s all ease;
                    }

                        .container-data-info table tr td:hover img
                        {
                            background: var(--c-tomato-cake);
                            color: var(--c-white);
                            transform: scale(0.9) rotate(180deg);
                        }
</style>