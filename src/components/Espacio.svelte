<script>
  import { bandera } from "../store/store.js";

  import Principal from "./Principal.svelte";
  import Cliente from "./Cliente.svelte";
  import Receptor from "./Receptor.svelte";
  import Proveedor from "./Proveedor.svelte";
  import Portal from "./Portal.svelte";
  import Operador from "./Operador.svelte";

  import Arbitraje from "./Arbitraje.svelte";
  import Remesas from "./Remesas.svelte";
  let bander;
  const establecerForm = bandera.subscribe(value => {
    bander = value;
  });

  const componentes = [
    { component: Principal },
    { component: Cliente },
    { component: Receptor },
    { component: Proveedor },
    { component: Portal },
    { component: Operador },

    { component: Arbitraje },
    { component: Remesas }
  ];
</script>

<style>
.Espacio{
  border-radius: 5px;
}
</style>

<div class="Espacio">
  <div class="bg-secondary">
    <h3 class="text-center">
      Registro de {componentes[bander].component.name.toString()}
    </h3>
    <svelte:component this={componentes[bander].component} />
  </div>
</div>
