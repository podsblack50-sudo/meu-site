from pathlib import Path
import shutil, zipfile, os

base = Path("/mnt/data/SmokePods_site")
img_dir = base / "img"
img_dir.mkdir(parents=True, exist_ok=True)

# As 5 imagens enviadas pelo usuário nesta conversa, na mesma ordem.
source_images = [
    ("/mnt/data/B8CF824F-1FB1-4F20-86B2-25CA9810E19B.jpeg", "produto-1.jpg"),
    ("/mnt/data/AEB341B6-F801-4961-913B-B7EF376DE3BD.jpeg", "produto-2.jpg"),
    ("/mnt/data/0A7CCBB2-67E2-44E8-A785-B63D8AA4238E.jpeg", "produto-3.jpg"),
    ("/mnt/data/24215F8D-6D78-454A-851B-9B4149626AA6.jpeg", "produto-4.jpg"),
    ("/mnt/data/6770FC42-C4D0-4210-A21D-0EFD938FFEE6.jpeg", "produto-5.jpg"),
]

for src, name in source_images:
    shutil.copy2(src, img_dir / name)

html = r'''<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#080812">
  <title>SmokePods — Estilo único. Do seu jeito.</title>
  <style>
    :root{
      --bg:#070711;
      --card:#101022;
      --card2:#15152d;
      --purple:#8b5cf6;
      --blue:#3b82f6;
      --text:#fff;
      --muted:#a7a7bd;
      --line:rgba(139,92,246,.25);
    }
    *{box-sizing:border-box}
    html{scroll-behavior:smooth}
    body{
      margin:0;
      font-family:Inter,ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif;
      color:var(--text);
      background:
        radial-gradient(circle at 10% 0%,rgba(59,130,246,.20),transparent 35%),
        radial-gradient(circle at 90% 10%,rgba(139,92,246,.22),transparent 35%),
        var(--bg);
    }
    a{text-decoration:none;color:inherit}
    .wrap{width:min(1080px,92%);margin:auto}
    header{
      position:sticky;top:0;z-index:10;
      background:rgba(7,7,17,.78);
      backdrop-filter:blur(16px);
      border-bottom:1px solid var(--line);
    }
    nav{
      min-height:70px;display:flex;align-items:center;justify-content:space-between;
    }
    .logo{
      font-size:25px;font-weight:900;letter-spacing:-1px;
      background:linear-gradient(90deg,#60a5fa,#a78bfa);
      -webkit-background-clip:text;background-clip:text;color:transparent;
    }
    .navlinks{display:flex;gap:24px;color:#ddd;font-size:14px}
    .navlinks a:hover{color:#fff}
    .hero{
      min-height:620px;display:grid;place-items:center;text-align:center;
      padding:70px 0 55px;
    }
    .badge{
      display:inline-block;padding:8px 13px;border:1px solid var(--line);
      border-radius:999px;background:rgba(139,92,246,.09);color:#c4b5fd;
      font-size:13px;font-weight:700;
    }
    h1{font-size:clamp(44px,10vw,82px);line-height:.95;margin:20px 0 18px;letter-spacing:-4px}
    .gradient{
      background:linear-gradient(90deg,#60a5fa,#8b5cf6,#c084fc);
      -webkit-background-clip:text;background-clip:text;color:transparent;
    }
    .hero p{max-width:650px;margin:0 auto;color:var(--muted);font-size:18px;line-height:1.6}
    .cta{
      display:inline-flex;margin-top:28px;padding:15px 25px;border-radius:14px;
      background:linear-gradient(135deg,var(--blue),var(--purple));
      font-weight:900;box-shadow:0 15px 40px rgba(99,102,241,.25);
    }
    section{padding:55px 0}
    .section-title{text-align:center;font-size:34px;margin:0 0 10px}
    .section-sub{text-align:center;color:var(--muted);margin:0 0 32px}
    .products{
      display:grid;grid-template-columns:repeat(2,minmax(0,1fr));gap:20px;
    }
    .product{
      overflow:hidden;border:1px solid var(--line);border-radius:22px;
      background:linear-gradient(180deg,rgba(21,21,45,.92),rgba(11,11,25,.95));
      box-shadow:0 20px 60px rgba(0,0,0,.25);
    }
    .photo{
      width:100%;aspect-ratio:1/1;object-fit:cover;display:block;
      background:#fff;
    }
    .info{padding:20px}
    .tag{font-size:12px;color:#a5b4fc;text-transform:uppercase;letter-spacing:1.5px;font-weight:800}
    .name{font-size:22px;font-weight:850;margin:7px 0}
    .desc{color:var(--muted);font-size:14px;line-height:1.5;margin:0 0 17px}
    .bottom{display:flex;align-items:center;justify-content:space-between;gap:12px}
    .price{font-size:23px;font-weight:900}
    .buy{
      border:0;color:#fff;font-weight:850;cursor:pointer;
      padding:12px 18px;border-radius:12px;
      background:linear-gradient(135deg,#2563eb,#7c3aed);
    }
    .about{
      border:1px solid var(--line);border-radius:24px;padding:28px;
      background:linear-gradient(135deg,rgba(59,130,246,.08),rgba(139,92,246,.10));
    }
    .about p{color:#c8c8d8;line-height:1.7;margin:8px 0}
    footer{border-top:1px solid var(--line);padding:30px 0;text-align:center;color:#85859a;font-size:13px}
    .toast{
      position:fixed;left:50%;bottom:24px;transform:translate(-50%,120px);
      background:#17172a;border:1px solid #3d3d65;color:#fff;padding:14px 18px;
      border-radius:14px;z-index:30;transition:.25s;box-shadow:0 15px 50px #0008;
      width:min(90%,420px);text-align:center;
    }
    .toast.show{transform:translate(-50%,0)}
    @media(max-width:700px){
      .navlinks{gap:12px;font-size:12px}
      .hero{min-height:560px;padding-top:50px}
      h1{letter-spacing:-2px}
      .hero p{font-size:16px}
      .products{grid-template-columns:1fr}
      .product:first-child{grid-column:auto}
      .wrap{width:min(92%,520px)}
      section{padding:45px 0}
    }
  </style>
</head>
<body>
  <header>
    <div class="wrap">
      <nav>
        <a class="logo" href="#">SmokePods</a>
        <div class="navlinks">
          <a href="#produtos">Produtos</a>
          <a href="#sobre">Sobre</a>
        </div>
      </nav>
    </div>
  </header>

  <main>
    <section class="hero">
      <div class="wrap">
        <span class="badge">PERSONALIZADOS • FEITOS À MÃO</span>
        <h1>Estilo único.<br><span class="gradient">Do seu jeito.</span></h1>
        <p>Conheça a coleção SmokePods. Um visual marcante, moderno e personalizado para quem gosta de ter algo diferente.</p>
        <a class="cta" href="#produtos">Ver produtos</a>
      </div>
    </section>

    <section id="produtos">
      <div class="wrap">
        <h2 class="section-title">Nossos produtos</h2>
        <p class="section-sub">Escolha seu modelo favorito — <strong>R$ 70,00</strong></p>

        <div class="products">
          <article class="product">
            <img class="photo" src="img/produto-1.jpg" alt="Produto personalizado SmokePods 1">
            <div class="info">
              <div class="tag">SmokePods</div><div class="name">Modelo Blue</div>
              <p class="desc">Produto personalizado com acabamento exclusivo.</p>
              <div class="bottom"><span class="price">R$ 70,00</span><button class="buy" onclick="comprar('Modelo Blue')">Quero este</button></div>
            </div>
          </article>

          <article class="product">
            <img class="photo" src="img/produto-2.jpg" alt="Produto personalizado SmokePods 2">
            <div class="info">
              <div class="tag">SmokePods</div><div class="name">Modelo Color</div>
              <p class="desc">Design colorido e visual personalizado.</p>
              <div class="bottom"><span class="price">R$ 70,00</span><button class="buy" onclick="comprar('Modelo Color')">Quero este</button></div>
            </div>
          </article>

          <article class="product">
            <img class="photo" src="img/produto-3.jpg" alt="Produto personalizado SmokePods 3">
            <div class="info">
              <div class="tag">SmokePods</div><div class="name">Modelo Custom</div>
              <p class="desc">Uma opção diferente para sua coleção.</p>
              <div class="bottom"><span class="price">R$ 70,00</span><button class="buy" onclick="comprar('Modelo Custom')">Quero este</button></div>
            </div>
          </article>

          <article class="product">
            <img class="photo" src="img/produto-4.jpg" alt="Produto personalizado SmokePods 4">
            <div class="info">
              <div class="tag">SmokePods</div><div class="name">Modelo Black</div>
              <p class="desc">Visual preto e elegante com acabamento marcante.</p>
              <div class="bottom"><span class="price">R$ 70,00</span><button class="buy" onclick="comprar('Modelo Black')">Quero este</button></div>
            </div>
          </article>

          <article class="product">
            <img class="photo" src="img/produto-5.jpg" alt="Produto personalizado SmokePods 5">
            <div class="info">
              <div class="tag">SmokePods</div><div class="name">Modelo Silver</div>
              <p class="desc">Design premium para completar a coleção.</p>
              <div class="bottom"><span class="price">R$ 70,00</span><button class="buy" onclick="comprar('Modelo Silver')">Quero este</button></div>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="sobre">
      <div class="wrap">
        <div class="about">
          <h2>SmokePods</h2>
          <p>Personalização, estilo e identidade em cada peça.</p>
          <p>Confira os modelos disponíveis e escolha o seu favorito.</p>
        </div>
      </div>
    </section>
  </main>

  <footer>© 2026 SmokePods — Todos os direitos reservados.</footer>

  <div id="toast" class="toast"></div>
  <script>
    function comprar(modelo){
      const toast=document.getElementById('toast');
      toast.textContent='Você escolheu: '+modelo+' — R$ 70,00. Entre em contato para finalizar o pedido.';
      toast.classList.add('show');
      setTimeout(()=>toast.classList.remove('show'),3500);
    }
  </script>
</body>
</html>
'''

(base / "index.html").write_text(html, encoding="utf-8")

readme = """# SmokePods

Site responsivo da SmokePods, preparado para GitHub Pages.

Arquivos:
- index.html
- img/produto-1.jpg até img/produto-5.jpg

Preço exibido: R$ 70,00.

Para publicar no GitHub Pages, envie o index.html e a pasta img para o mesmo repositório.
"""
(base / "README.txt").write_text(readme, encoding="utf-8")

zip_path = Path("/mnt/data/SmokePods_site_pronto.zip")
with zipfile.ZipFile(zip_path, "w", zipfile.ZIP_DEFLATED) as z:
    for p in base.rglob("*"):
        if p.is_file():
            z.write(p, p.relative_to(base.parent))

print(f"Site criado: {base / 'index.html'}")
print(f"Pacote pronto: {zip_path}")
