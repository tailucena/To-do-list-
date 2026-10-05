<!DOCTYPE html>  
<html lang="pt">  
<head>  
    <style>  
  body {  
    background: linear-gradient(45deg, #E37083, #F49AA2);  
    min-height: 100vh;  
    margin: 0;  
    }  
    .container {  
      width: 70%;  
      margin: 10px ;  
      height: 35hv;  
      padding: 40px;  
      background-color: #fff;  
      border: 7px solid #A8BF8A;  
      border-radius: 50px;  
      text-align-items: center;  
      position: absolut;  
      box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);  
    }  
    
    .concluida {
    text-decoration: line-through;
    opacity: 0.5;
}
  </style>  
  <meta charset="UTF-8">  
  <meta name="viewport" content="width=device-width, initial-scale=0.9">  
  <title>Minha lista de tarefas</title>  </head>  
<body>  
  <div class="container">  
    <h1>Minha lista de tarefas</h1>  
    <input type="text" id="tarefa" placeholder="Adicionar tarefa">  
    <button id="adicionar">+</button>  
    <button id="excluir-todas">Excluir todas</button>  
    <ul id="lista-tarefas"></ul>  
  </div>   
  
   <script>
    const inputTarefa = document.getElementById('tarefa');
    const botaoAdicionar = document.getElementById('adicionar');
    const botaoExcluirTodas = document.getElementById('excluir-todas');
    const listaTarefas = document.getElementById('lista-tarefas');

    botaoAdicionar.addEventListener('click', () => {

        const tarefa = inputTarefa.value;

        if (tarefa !== '') {

            const itemLista = document.createElement('li');

            itemLista.textContent = tarefa;

            itemLista.addEventListener('click', () => {
                itemLista.classList.toggle('concluida');
            });

            const botaoExcluir = document.createElement('button');
            botaoExcluir.textContent = 'Excluir';

            botaoExcluir.addEventListener('click', () => {
                itemLista.remove();
            });

            itemLista.appendChild(botaoExcluir);
            listaTarefas.appendChild(itemLista);

            inputTarefa.value = '';
        }
    });

    botaoExcluirTodas.addEventListener('click', () => {
        listaTarefas.innerHTML = '';
    });
</script>
   </body>  
</html>
