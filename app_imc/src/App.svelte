<script>
	// Variáveis de estado
	let peso = 0;      // Peso do usuário
	let altura = 0;    // Altura do usuário
	let imc = 0;       // Índice de Massa Corporal
  
	// Função para calcular o IMC
	function calcularIMC() {
	  if (peso > 0 && altura > 0) {
		imc = (peso / Math.pow(altura, 2)).toFixed(2);
	  } else {
		imc = 0;
	  }
	}

  </script>
  
  <main style="background-color: #ffff66;">
	<h1>Calculadora de IMC</h1>
	<label>
	  Peso (kg): <input type="number" bind:value={peso} on:input={calcularIMC} />
	</label>
	<label>
	  Altura (m): <input type="number" bind:value={altura} on:input={calcularIMC} />
	</label>
	{#if imc > 0}
	  <p>Seu IMC é {imc}</p>
	  {#if imc <= 18.5}
	    <p class="below-weight">Você está abaixo do peso</p>
	  {/if}
	  {#if imc >= 18.6 && imc <= 24.9}
	    <p class="ideal-weight">Peso Ideal!! Parebéns :)</p>
	  {/if}
	  {#if imc >= 25 && imc <= 29.9}
	    <p class="slightly-overweight">Levemente acima do peso</p>
	  {/if}
	  {#if imc >= 30 && imc <= 34.9}
	    <p class="obesity-1">Obesidade grau 1</p>
	  {/if}
	  {#if imc >= 35 && imc <= 39.9}
	    <p class="obesity-2">Obesidade grau 2 - Severa :(</p>
	  {/if}
	  {#if imc >= 40}
	    <p class="obesity-3">Obesidade grau 3 - Mórbida :(</p>
	  {/if}
	{/if}
  </main>
  
  <style>
	main {
	  font-family: sans-serif;
	  text-align: center;
	  padding: 10rem;
	  background-color: #ffff66;
	}

  
	h1 {
	  font-size: 1.5rem;
	  margin-bottom: 1rem;
	}
  
	label {
	  display: block;
	  margin-bottom: 0.5rem;
	}
  
	input {
	  padding: 0.25rem;
	}

	/* Cores para cada classificação */
    .below-weight {
		color: #66ff66;
    }

    .ideal-weight {
		color: green;
    }

    .slightly-overweight {
        color: #006600;
    }

    .obesity-1 {
       color: #ff3300;
    }

    .obesity-2 {
       color: red;
    }

    .obesity-3 {
       color: #cc0000;
    }
  </style>
  