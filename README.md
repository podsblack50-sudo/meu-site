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
      background:
        radial-gradient(circle at top, #24104f 0%, #0b1020 45%, #05070d 100%);
      color: white;
      text-align: center;
      min-height: 100vh;
    }

    header {
      padding: 35px 20px;
      background: linear-gradient(135deg, #080b15, #171044, #062b61);
      border-bottom: 2px solid #6c2cff;
      box-shadow: 0 0 25px rgba(82, 45, 255, 0.4);
    }

    h1 {
      margin: 0;
      font-size: 38px;
      font-weight: 900;
      text-shadow:
        0 0 10px #2583ff,
        0 0 25px #7b2cff;
    }

    .subtitulo {
      margin: 10px 0 0;
      color: #bfc9ff;
      font-size: 17px;
    }

    .titulo {
      margin: 45px 15px 10px;
      font-size: 32px;
    }

    .descricao {
      margin: 0 20px 30px;
      color: #b9b9c9;
      font-size: 18px;
    }

    .produtos {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(280px, 380px));
      gap: 25px;
      justify-content: center;
      padding: 0 15px;
    }

    .produto {
      padding: 22px;
      background: linear-gradient(
        145deg,
        rgba(30, 36, 70, 0.95),
        rgba(13, 17, 35, 0.98)
      );

      border: 1px solid #633cff;
      border-radius: 25px;

      box-shadow:
        0 0 15px rgba(38, 131, 255, 0.25),
        0 0 35px rgba(123, 44, 255, 0.18);
    }

    .produto img {
      width: 100%;
      height: 300px;
      object-fit: contain;
      border-radius: 18px;
      margin-bottom: 15px;
      background: #070a14;
    }

    .produto h2 {
      margin: 5px 0 10px;
      font-size: 28px;
    }

    .produto p {
      color: #c4c8d8;
      font-size: 17px;
      margin-bottom: 20px;
    }

    .preco {
      font-size: 30px;
      font-weight: bold;
      color: #4da3ff;
      text-shadow: 0 0 15px rgba(77, 163, 255, 0.6);
      margin: 20px 0;
    }

    .botao {
      display: block;
      padding: 17px 20px;

      background: linear-gradient(
        90deg,
        #1769ff,
        #6c2cff,
        #9b35ff
      );

      color: white;
      text-decoration: none;
      border-radius: 15px;
      font-size: 18px;
      font-weight: bold;

      box-shadow:
        0 0 15px rgba(37, 131, 255, 0.5),
        0 0 25px rgba(123, 44, 255, 0.35);
    }

    .botao:active {
      transform: scale(0.97);
    }

    footer {
      margin-top: 50px;
      padding: 25px 15px;
      color: #777b8c;
      font-size: 14px;
      border-top: 1px solid #252a40;
    }
  </style>
</head>

<body>

  <header>
    <h1>SmokePods</h1>
    <p class="subtitulo">Estilo único. Do seu jeito.</p>
  </header>

  <h2 class="titulo">Nossos produtos</h2>

  <p class="descricao">
    Confira nossos modelos personalizados.
  </p>

  <main class="produtos">

    <!-- PRODUTO 1 -->
    <div class="produto">
      <img src="pod1.jpg" alt="Pod personalizado 1">

      <h2>Pod personalizado</h2>

      <p>Modelo personalizado à mão.</p>

      <div class="preco">R$ 69,99</div>

      <a class="botao" href="#">
        COMPRAR AGORA
      </a>
    </div>


    <!-- PRODUTO 2 -->
    <div class="produto">
      <img src="pod2.jpg" alt="Pod personalizado 2">

      <h2>Pod personalizado</h2>

      <p>Modelo personalizado à mão.</p>

      <div class="preco">R$ 69,99</div>

      <a class="botao" href="#">
        COMPRAR AGORA
      </a>
    </div>


    <!-- PRODUTO 3 -->
    <div class="produto">
      <img src="pod3.jpg" alt="Pod personalizado 3">

      <h2>Pod personalizado</h2>

      <p>Modelo personalizado à mão.</p>

      <div class="preco">R$ 69,99</div>

      <a class="botao" href="#">
        COMPRAR AGORA
      </a>
    </div>


    <!-- PRODUTO 4 -->
    <div class="produto">
      <img src="pod4.jpg" alt="Pod personalizado 4">

      <h2>Pod personalizado</h2>

      <p>Modelo personalizado à mão.</p>

      <div class="preco">R$ 69,99</div>

      <a class="botao" href="#">
        COMPRAR AGORA
      </a>
    </div>


    <!-- PRODUTO 5 -->
    <div class="produto">
      <img src="pod5.jpg" alt="Pod personalizado 5">

      <h2>Pod personalizado</h2>

      <p>Modelo personalizado à mão.</p>

      <div class="preco">R$ 69,99</div>

      <a class="botao" href="#">
        COMPRAR AGORA
      </a>
    </div>

  </main>

  <footer>
    © 2026 SMOKEPODS — Todos os direitos reservados.
  </footer>

</body>
</html>