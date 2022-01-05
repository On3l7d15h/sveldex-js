<script>
    // your script goes here
    const handleOnClick = () => {
        Swal.fire({
            title: "Sveldex v1.0",
            text: "Primera Versión de la Aplicación de una Pokedex desarrollada en Svelte © On3l7d15h",
            icon: "success"
        })
    }
</script>

<div class="nav">
    <section class="nav-title">
        <h1> Sveldex! </h1>
    </section>
    <section class="nav-about">
        <p>
            Esta Aplicación fue desarrollada con Svelte, su función principal es la de poder
            tener información sobre tus pokemones favoritos!
        </p>
        <button on:click={handleOnClick}>Info!</button>
    </section>
</div>

<style>
    /* Navbar Styles! */

    .nav
    {
        background: var(--c-gray);
        max-width: 20%;
        width: 100%;
        height:100vh;
        display: flex;
        flex-direction: column;
        flex-wrap: nowrap;
        justify-content: space-between;
        overflow: hidden;
        box-shadow: 0 2px 8px 0 var(--c-black-trans);
    }

        .nav .nav-title
        {
            width: 100%;
            height: calc(100vh - 75%);
            color: var(--c-white);
            background: var(--c-tomato);
            display: flex;
            flex-direction: row;
            flex-wrap: nowrap;
            justify-content: center;
            align-items: center;
            font-size: 48px;
            text-align: center;
        }

        .nav .nav-about
        {
            font-size: 18px;
            color: var(--c-white);
            width: 100%;
            height: calc(100vh - 25%);
            display: flex;
            flex-direction: column;
            flex-wrap: nowrap;
            text-align: center;
            justify-content: center;
            align-items: center;
        }

            .nav .nav-about button
            {
                border: 2px solid var(--c-white);
                outline: 0;
                color: var(--c-white);
                background: transparent;
                padding: 5px 15px;
                border-radius: 5px;
                margin: 10px;
                font-weight: bold;
                cursor: pointer;
                transition: .6s all ease;
                position: relative;
                top: -50px;
                opacity: 0;
            }

                .nav .nav-about:hover button
                {
                    top: 10px;
                    opacity: 1;
                }

                .nav .nav-about button:hover
                {
                    background: var(--c-white);
                    color: var(--c-tomato);
                }

</style>