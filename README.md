<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>SmokePods</title>

  <style>
    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: Arial, sans-serif;
      background: radial-gradient(
        circle at top,
        #35106b 0%,
        #11152d 45%,
        #03050b 100%
      );
      color: white;
      text-align: center;
      min-height: 100vh;
    }

    header {
      padding: 40px 20px;
      background: linear-gradient(
        135deg,
        #050712,
        #32106b,
        #073b80
      );
      border-bottom: 2px solid #8b35ff;
      box-shadow: 0 0 30px rgba(117, 45, 255, 0.5);
    }

    header h1 {
      margin: 0;
      font-size: 42px;
      font-weight: 900;
      text-shadow:
        0 0 10px #168cff,
        0 0 25px #a62cff;
    }

    .subtitulo {
      margin-top: 10px;
      color: #c8d2ff;
      font-size: 18px;
    }

    .titulo {
      margin: 40px 15px 10px;
      font-size: 32px;
      text-shadow: 0 0 15px #713cff;
    }

    .descricao {
      color: #bfc3d5;
      font-size: 17px;
      margin: 0 20px 35px;
    }

    .produtos {
      display: grid;
      grid-template-columns: repeat(
        auto-fit,
        minmax(280px, 360px)
      );
      justify-content: center;
      gap: 25px;
      padding: 0 15px;
    }

    .produto {
      background: linear-gradient(
        145deg,
        rgba(35, 42, 82, 0.98),
        rgba(10, 13, 28, 0.99)
      );

      border: 1px solid #743cff;
      border-radius: 25px;
      padding: 20px;

      box-shadow:
        0 0 15px rgba(40, 130, 255, 0.25),
        0 0 35px rgba(130, 45, 255, 0.2);
    }

    .produto img {
      width: 100%;
      height: 280px;
      object-fit: contain;
      border-radius: 18px;
      background: #050711;
      display: block;
      margin-bottom: 18px;
    }

    .produto h2 {
      font-size: 27px;
      margin: 10px 0;
    }

    .produto p {
      color: #c8cce0;
      font-size: 16px;
    }

    .preco {
      font-size: 31px;
      font-weight: bold;
      color: #4da5ff;
      margin: 20px 0;
      text-shadow: 0 0 15px rgba(77, 165, 255, 0.6);
    }

    .botao {
      display: block;
      padding: 16px;
      border-radius: 15px;

      background: linear-gradient(
        90deg,
        #1769ff,
        #702cff,
        #a332ff
      );

      color: white;
      text-decoration: none;
      font-size: 17px;
      font-weight: bold;

      box-shadow:
        0 0 15px rgba(30, 130, 255, 0.5),
        0 0 25px rgba(130, 40, 255, 0.4);
    }

    footer {
      margin-top: 50px;
      padding: 25px 15px;
      color: #777c91;
      border-top: 1px solid #272c45;
      font-size: 14px;
    }
  </style>
</head>

<body>

  <header>
    <h1>SmokePods</h1>
    <p class="subtitulo">
      Estilo único. Do seu jeito.
    </p>
  </header>

  <h2 class="titulo">💜 Nossos Produtos</h2>

  <p class="descricao">
    Confira nossos modelos personalizados.
  </p>

  <main class="produtos">

    <!-- PRODUTO 1 -->
    <div class="produto">
      <img
        src="1cb2a01b-6d25-455f-8897-b1eb682ac56a.jpeg"
        alt="Produto personalizado 1"
      >

      <h2>Pod personalizado</h2>

      <p>
        Modelo exclusivo personalizado à mão.
      </p>

      <div class="preco">
        R$ 70,00
      </div>

      <a class="botao" href="#">
        COMPRAR
      </a>
    </div>


    <!-- PRODUTO 2 -->
    <div class="produto">
      <img
        src="2b899fb9-a626-4208-9bb3-eb2e8d70127d.jpeg"
        alt="Produto personalizado 2"
      >

      <h2>Pod personalizado</h2>

      <p>
        Modelo exclusivo personalizado à mão.
      </p>

      <div class="preco">
        R$ 70,00
      </div>

      <a class="botao" href="#">
        COMPRAR
      </a>
    </div>


    <!-- PRODUTO 3 -->
    <div class="produto">
      <img
        src="52e4f985-01a5-490d-a412-edc89b78dc41.jpeg"
        alt="Produto personalizado 3"
      >

      <h2>Pod personalizado</h2>

      <p>
        Modelo exclusivo personalizado à mão.
      </p>

      <div class="preco">
        R$ 70,00
      </div>

      <a class="botao" href="#">
        COMPRAR
      </a>
    </div>


    <!-- PRODUTO 4 -->
    <div class="produto">
      <img
        src="8cbeb1d1-5c12-4b4c-ae4a-dbf56ee776cb.jpeg"
        alt="Produto personalizado 4"
      >

      <h2>Pod personalizado</h2>

      <p>
        Modelo exclusivo personalizado à mão.
      </p>

      <div class="preco">
        R$ 70,00
      </div>

      <a class="botao" href="#">
        COMPRAR
      </a>
    </div>


    <!-- PRODUTO 5 -->
    <div class="produto">
      <img
        src="e2ea8864-0bf0-42a5-b8d9-882fa45c4026.jpeg"
        alt="Produto personalizado 5"
      >

      <h2>Pod personalizado</h2>

      <p>
        Modelo exclusivo personalizado à mão.
      </p>

      <div class="preco">
        R$ 70,00
      </div>

      <a class="botao" href="#">
        COMPRAR
      </a>
    </div>

  </main>

  <footer>
    © 2026 SMOKEPODS — Todos os direitos reservados.
  </footer>

</body>
</html>