<script>
    let tareas = [];
    let nombreTarea = '';

    function agregarTarea(event){
        if(event.key === 'Enter'){
            tareas.push(nombreTarea);
            console.log(tareas);
            tareas = tareas;
            nombreTarea = '';
        }
    }
</script>

<div>
   <div class="container mt-5">
       <div class="row">
           <div class="col-lg-8 offset-lg-2">
              <input type="text" class="form-control form-control-lg"
                    on:keydown={agregarTarea}
                    bind:value={nombreTarea}    
                    placeholder="Ingresar tarea..">
              <br>
            </div>
           
           <div class="col-lg-6 offset-lg-3">
               {#if tareas.length === 0}
               <div class="card p-2">
                   <h6>No hay tareas para mostrar</h6>
               </div>
               {/if}

               <ul class="list-group">
                {#each tareas as tarea}
                   <li class="list-group-item d-flex justify-content-between">
                       <span class="cursor">
                            <i class="far fa-circle"></i>
                       </span>
                        <h5>{ tarea }</h5>
                        <span class="cursor text-danger">
                            <i class="fas fa-trash-alt"></i>
                        </span>
                   </li>
                   {/each}
               </ul>
           </div>
       </div>
   </div>
</div>

<style>
    .form-control-lg {
        font-size: 1.8rem;
    }
    input {
        text-align: center;
    }

    .cursor {
        cursor: pointer;
    }
</style>