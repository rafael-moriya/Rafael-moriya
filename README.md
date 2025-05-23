 oi, meu nome é Rafael Moriya
 tenho 21 anos
 - fiz curso técnico de desenvolvimento de sistemas(DS) na ETEC ZL
 - fiz curso de logica de programaçao na USP leste
 - Atualmente faço faculdade de análise e desenvolvimento de sistemas(ADS) na FATEC ZL
 - sou monitor de algoritimos e logica de programação

   </a> 
    <a href="https://github.com/rafael-moriya?tab=repositories&sort=stargazers">
        <img 
            alt="Total de estrelas" 
            title="Total de estrelas GitHub" 
            src="https://custom-icon-badges.demolab.com/github/stars/rafael-moriya?color=55960c&style=for-the-badge&labelColor=488207&logo=star&label=estrelas"
        />
    </a>
    <a href="https://github.com/rafael-moriya?tab=followers">
        <img 
            alt="Seguidores" 
            title="Me siga no GitHub" 
            src="https://custom-icon-badges.demolab.com/github/followers/rafael-moriya?color=236ad3&labelColor=1155ba&style=for-the-badge&logo=github&label=Seguidores&logoColor=white"
        />
    </a>
</p>

### 🤖 Linguagens e Tecnologias

<img 
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/java/java-original-wordmark.svg" 
/>
          
<img 
align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;" 
src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/visualbasic/visualbasic-original.svg"
/>
          

<img 
align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;"
src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original-wordmark.svg" 
/>
          

<img 
align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;"
src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original-wordmark.svg" 
/>
          
<img
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;"
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original-wordmark.svg"
   />
<br/>
<br/>      

### 📊 Estatísticas

<p>
  <img 
    align="left" 
    alt="GitHub Stats" 
    height="200" 
    style="padding-right: 10px;" 
    src="https://github-readme-stats.vercel.app/api?username=rafael-moriya&show_icons=true&theme=tokyonight&include_all_commits=true&locale=pt-br" 
  />

<img 
      align="left" 
      alt="GitHub Stats" 
      height="200" 
      src="https://github-readme-stats.vercel.app/api/top-langs/?username=rafael-moriya&theme=tokyonight&layout=compact&custom_title=Tecnologias&langs_count=9" 
  />

</p>
<br/>
<br/>

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
    
    - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

