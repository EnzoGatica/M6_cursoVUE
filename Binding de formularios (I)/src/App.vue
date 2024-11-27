<template>
    <div class="carnet">
      <aside>
        <div>
          <span>CEDULA DE INDENTIDAD</span>
          <img width="40" src="/chile_bandera.png" alt="" />
        </div>

        <img src="/foto_elon.jpg" alt="" />
        <p>RUN {{ run }}</p>
      </aside>

      <main>
        <header>
          <p>REPUBLICA DE CHILE</p>
          <span>SERVICIO DE REGISTRO CIVIL E IDENTIFICACIÓN</span>
        </header>
        <section>
        <div class="grid-2-colums">
          <article>
            <header>APELLIDOS</header>
            <span>{{ apellidos }}</span>
          </article>
        </div>
        <div class="grid-2-colums">
          <article>
            <header>NOMBRES</header>
            <span>{{ nombres }}</span>
          </article>
        </div>
          <div class="grid-2-colums">
            <article>
              <header>NACIONALIDAD</header>
              <span>{{ nacionalidad }}</span>
            </article>
            <article>
              <header>SEXO</header>
              <span>{{ sexo }}</span>
            </article>
          </div>
          <div class="grid-2-colums">
            <article>
              <header>FECHA DE NACIMIENTO</header>
              <span>{{ fechaNacimiento }}</span>
            </article>
            <article>
              <header>NÙMERO DOCUMENTO</header>
              <span>{{ numeroDocumento }}</span>
            </article>
          </div>
          <div class="grid-2-colums">
            <article>
              <header>FECHA DE EMISIÒN</header>
              <span>{{ fechaEmision }}</span>
            </article>
            <article>
              <header>FECHA DE VENCIMIENTO</header>
              <span>{{ fechaVencimiento }}</span>
            </article>
          </div>
          <div class="grid-2-colums">
          <article>
            <header>FIRMA DEL TITULAR</header>
            <span>{{ firma }}</span>
          </article>
        </div>
        </section>
      </main>
    </div>
  </template>
  
  <script>
  import chileBandera from '/chile_bandera.png';
  import fotoElon from '/foto_elon.jpg';
  
  export default {
    data() {
      return {
        run: '22.222.222-2',
        apellidos: 'Musk',
        nombres: 'Elon Reeve',
        nacionalidad: 'Sudafricano',
        sexo: 'M',
        fechaNacimiento: '28 JUN 1971',
        numeroDocumento: '222.222.222',
        fechaEmision: '01 ENE 2025',
        fechaVencimiento: '01 ENE 2030',
        firma: 'X Æ A-12',
        chileBandera,
        fotoElon
      };
    }
  };
  </script>
  

  