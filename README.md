## Hello, stranger. :stuck_out_tongue_winking_eye:

I'm a geneticist biologist 🧬 who decided to venture into the world of bioinformatics 🖥️. 


#### I usually work with: 
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/r/r-original.svg" width="40" height="40"/>   <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/rstudio/rstudio-original.svg" width="40" height="40"/><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/linux/linux-original.svg" width="40" height="40"/>


#### I know the basics of:
<img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/putty/putty-original.svg" width="40" height="40"/>   <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/filezilla/filezilla-plain.svg" width="40" height="40"/>   <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/googlecloud/googlecloud-original.svg" width="40" height="40"/>   <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" width="40" height="40"/>   <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" width="40" height="40"/> 




![Snake animation](https://github.com/gcgiudicelli/gcgiudicelli/blob/output/github-contribution-grid-snake.svg)
<div>
<a href="https://github.com/gcgiudicelli">
<img height="140em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=gcgiudicelli&layout=compact&langs_count=7&theme=aura"/>
<img height="140em" src="https://github-readme-stats.vercel.app/api?username=gcgiudicelli&show_icons=true&theme=aura&include_all_commits=true&count_private=true"/>
</div>




name: generate animation

on:
  # run automatically every 24 hours
  schedule:
    - cron: "0 */24 * * *" 
  
  # allows to manually run the job at any time
  workflow_dispatch:
  
  # run on every push on the master branch
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
      # generates a snake game from a github user (<github_user_name>) contributions graph, output a svg animation at <svg_out_path>
      - name: generate github-contribution-grid-snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: |
            dist/github-contribution-grid-snake.svg
            dist/github-contribution-grid-snake-dark.svg?palette=github-dark
          
          
      # push the content of <build_dir> to a branch
      # the content will be available at https://raw.githubusercontent.com/<github_user>/<repository>/<target_branch>/<file> , or as github page
      - name: push github-contribution-grid-snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

















<!--
HOW TO CREATE A README FILE: https://www.alura.com.br/artigos/como-criar-um-readme-para-seu-perfil-github?gclid=Cj0KCQjwn9CgBhDjARIsAD15h0BftHMQIJNKiofVvJ0JjiBz-AoUIpuG1o4YqX2O5jBF2QII6RQHaUEaAgMsEALw_wcB
GITHUB EMOJIS: https://github.com/hideraldus13/github-emoji

**gcgiudicelli/gcgiudicelli** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.
Here are some ideas to get you started:
- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
