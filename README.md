<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=00bfbf&height=120&section=header"/>

[![Typing SVG](https://readme-typing-svg.herokuapp.com/?color=00bfbf&size=35&center=true&vCenter=true&width=1000&lines=HELLO,+MY+NAME+is+Gabriel;Be+Welcome!+:%29)](https://git.io/typing-svg)

<div align="center">  
  <img width="49%" height="195px" src="https://github-readme-stats.vercel.app/api?username=CasteloCodeStudio&show_icons=true&count_private=true&hide_border=true&title_color=00bfbf&icon_color=00bfbf&text_color=c9d1d9&bg_color=0d1117" alt="Matheus Maia Alvarez github stats" /> 
  <img width="41%" height="195px" src="https://github-readme-stats.vercel.app/api/top-langs/?username=CasteloCodeStudio&layout=compact&hide_border=true&title_color=00bfbf&text_color=00bfbf&bg_color=0d1117" />
</div>

![Github activity graph](https://github-readme-activity-graph.cyclic.app/graph?username=CasteloCodeStudio&theme=gotham)

<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=CasteloCodeStudio&theme=dracula&row=2&no-bg=true&column=3&margin-w=15&margin-h=15" />
</p>

<div align="center">  
<a href="https://www.instagram.com/imnotcastelo/" target="_blank"><img src="https://img.shields.io/badge/-Instagram-%23E4405F?style=for-the-badge&logo=instagram&logoColor=white"</a>
</div>
  
  <div align="center">
<br><p align="centre"><b>Visitors Count</b></p>  
<p align="center"><img align="center" src="https://profile-counter.glitch.me/{CasteloCodeStudio}/count.svg" /></p> 
<br></div>
  

<img width=100% src="https://capsule-render.vercel.app/api?type=waving&color=00bfbf&height=120&section=footer"/>

<canvas id="canvas" width="500" height="500"></canvas>

<script>
  function game() {
  // Cria um canvas
  const canvas = document.createElement("canvas");
  canvas.width = 500;
  canvas.height = 500;
  document.body.appendChild(canvas);

  // Cria um contexto de desenho
  const ctx = canvas.getContext("2d");

  // Inicializa a cobra
  let snake = new Snake([
    [250, 250],
    [249, 250],
    [248, 250],
  ]);

  // Inicializa a fruta
  let fruit = new Fruit();

  // Loop do jogo
  while (true) {
    // Atualiza a cobra
    snake.update();

    // Verifica se a cobra tocou na fruta
    if (snake.head === fruit.position) {
      // A cobra come a fruta
      snake.grow();
      // Gera uma nova fruta
      fruit = new Fruit();
    }

    // Verifica se a cobra tocou em si mesma ou nas bordas da tela
    if (snake.collidesWithSelf() || snake.collidesWithWalls()) {
      // O jogo termina
      break;
    }

    // Desenha a cobra
    ctx.fillStyle = "black";
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    for (const segment of snake.segments) {
      ctx.fillStyle = "green";
      ctx.fillRect(segment[0], segment[1], 10, 10);
    }

    // Desenha a fruta
    ctx.fillStyle = "red";
    ctx.fillRect(fruit.position[0], fruit.position[1], 10, 10);

    // Atualiza a tela
    window.requestAnimationFrame(() => {
      game();
    });
  }
}

// Inicia o jogo
game();
</script>
