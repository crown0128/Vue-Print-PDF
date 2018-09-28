<template>
  <div class="hello">
    <h1>{{ msg }}</h1> 
    <button @click="ImprimirSaldo">Consulta de Saldo</button> <br>
    <button @click="ImprimirOrden">Gestiones</button> <br>

    <p>
      For guide and recipes on how to configure / customize this project,<br>
      check out the
      <a href="https://cli.vuejs.org" target="_blank" rel="noopener">vue-cli documentation</a>.
    </p>
    <h3>Installed CLI Plugins</h3>
    <ul>
      <li><a href="https://github.com/vuejs/vue-cli/tree/dev/packages/%40vue/cli-plugin-babel" target="_blank" rel="noopener">babel</a></li>
    </ul>
    <h3>Essential Links</h3>
    <ul>
      <li><a href="https://vuejs.org" target="_blank" rel="noopener">Core Docs</a></li>
      <li><a href="https://forum.vuejs.org" target="_blank" rel="noopener">Forum</a></li>
      <li><a href="https://chat.vuejs.org" target="_blank" rel="noopener">Community Chat</a></li>
      <li><a href="https://twitter.com/vuejs" target="_blank" rel="noopener">Twitter</a></li>
      <li><a href="https://news.vuejs.org" target="_blank" rel="noopener">News</a></li>
    </ul>
    <h3>Ecosystem</h3>
    <ul>
      <li><a href="https://router.vuejs.org" target="_blank" rel="noopener">vue-router</a></li>
      <li><a href="https://vuex.vuejs.org" target="_blank" rel="noopener">vuex</a></li>
      <li><a href="https://github.com/vuejs/vue-devtools#vue-devtools" target="_blank" rel="noopener">vue-devtools</a></li>
      <li><a href="https://vue-loader.vuejs.org" target="_blank" rel="noopener">vue-loader</a></li>
      <li><a href="https://github.com/vuejs/awesome-vue" target="_blank" rel="noopener">awesome-vue</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {msg: String},
  methods:
  {
    
    ImprimirOrden()
    {
      $('<iframe>', {name: 'myiframe',class: 'printFrame'})
        .appendTo('body')
        .contents().find('body')
        .append(`
                  <style>
                  table, th, td {border: 1px solid black;border-collapse: collapse;}

                  th, td {padding: 5px;text-align: left;}

                  .imgCenter {display: block;margin-left: auto;margin-right: auto;width: 40%;}                  

                  .centerText { text-align: center}
                  .rightText { text-align: right}
                  .boldText {font-weight: bold;}
                  </style>    

          <img class="imgCenter" src='logonav.png' height="120px" width="160px" /> 
          <h4 class="centerText">Auto Consulta</h4> 
          <h3 class="centerText boldText">Consulta de Gestión</h3> 
          <table style="width:100%" >
            <tr>
              <th class="centerText">Descripción</th>
              <th class="centerText">Valor</th>
            </tr>
            <tr>
              <td>No. Orden</td>
              <td class="centerText">372707</td>
            </tr>
            <tr>
              <td>Fecha de la Orden</td>
              <td class="centerText" >28/09/2018</td>
            </tr>
            <tr>
              <td>Estado de la Orden</td>
              <td class="centerText boldText">FINALIZADA</td>
            </tr>     
            <tr>
              <td>Tipo de Orden</td>
              <td class="centerText">RECONEXIONES MANUALES AGUA</td>
            </tr>                                                             
          </table>          
          
        `);

        window.frames['myiframe'].focus();
        window.frames['myiframe'].print();

        setTimeout(() => { $(".printFrame").remove(); }, 1000);      
    },

    ImprimirSaldo()
    {
        $('<iframe>', {name: 'myiframe',class: 'printFrame'})
        .appendTo('body')
        .contents().find('body')
        .append(`
                  <style>
                  table, th, td {
                      border: 1px solid black;
                      border-collapse: collapse;
                  }
                  th, td {padding: 5px;text-align: left;}

                  .imgCenter {
                      display: block;
                      margin-left: auto;
                      margin-right: auto;
                      width: 40%;
                  }                    

                  .centerText { text-align: center}
                  .rightText { text-align: right}
                  .boldText {font-weight: bold;}
                  </style>    

          <img class="imgCenter" src='logonav.png' height="120px" width="160px" /> 
          <h4 class="centerText">Auto Consulta</h4> 
          <h3 class="centerText boldText">Consulta de Saldo</h3>           
          <table style="width:100%">
            <caption>Saldos al 09 Septiembre 2018</caption>
            <tr>
              <th class="centerText">Descripción</th>
              <th class="centerText">Valor</th>
            </tr>
            <tr>
              <td>No. Cliente</td>
              <td class="centerText">100</td>
            </tr>
            <tr>
              <td>No. Facturas Pendientes</td>
              <td class="centerText" >5</td>
            </tr>
            <tr>
              <td>Saldo Última Factura</td>
              <td class="rightText">500.00</td>
            </tr>     
            <tr>
              <td>Saldo Anterior</td>
              <td class="rightText">200.00</td>
            </tr>    
            <tr>
              <td>Intereses, Cortes y Multas</td>
              <td class="rightText">300.00</td>
            </tr>    
            <tr>
              <td>Letras y Pagare</td>
              <td class="rightText">4,000.00</td>
            </tr>   
            <tr>
              <td>Otros Saldos</td>
              <td class="rightText">8,000.56</td>
            </tr>    
            <tr>
              <td class="boldText">Saldo Total (Lempiras)</td>
              <td class="rightText boldText">13,000.56</td>
            </tr>                                                             
          </table>          
          
        `);

        window.frames['myiframe'].focus();
        window.frames['myiframe'].print();

        setTimeout(() => { $(".printFrame").remove(); }, 1000);
    },
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
