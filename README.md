# devbyansh
👨‍💻 Passionate Full-Stack Developer | Java • Spring Boot • React • Next.js • Tailwind
<br clear="both">

<h1 align="left">Hey there! 🙋‍♂️</h1>

###

<p align="left">I’m Ansh, a software engineer based in India...</p>

###

<h2 align="left">About me</h2>

###

<img align="right" height="200" src="https://i.pinimg.com/736x/21/a0/6c/21a06c4dbd317f4d60c1ad55b6cd6488.jpg"  />

###

<p align="left">If an idea sparks in my head, I love turning it into a working product — from concept to deployment.<br><br>My tech stack revolves around Java, Spring Boot, React, Next.js, Tailwind CSS.<br><br>I enjoy experimenting with new tools and frameworks to sharpen my craft and bring fresh ideas to life.</p>

###

<h2 align="left">I code with</h2>

###

<br clear="both">

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="40" alt="java logo"  />
  <img width="13" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" height="40" alt="react logo"  />
  <img width="13" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="javascript logo"  />
  <img width="13" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" height="40" alt="nextjs logo"  />
  <img width="13" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" height="40" alt="nodejs logo"  />
  <img width="13" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original-wordmark.svg" height="40" alt="tailwindcss logo"  />
  <img width="13" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" height="40" alt="spring logo"  />
</div>

###

<img src="https://raw.githubusercontent.com/anshhhr/anshhhr/output/snake.svg" alt="Snake animation" />

###

<br clear="both">

<div align="left">
  <a href="www.linkedin.com/in/anshrr" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/linkedin/default.svg" width="53" height="40" alt="linkedin logo"  />
  </a>
  <a href="https://www.instagram.com/anshhh_r?igsh=MW93MWt0NTdsM2Vhbw==" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/instagram/default.svg" width="53" height="40" alt="instagram logo"  />
  </a>
  <a href="mailto:rahangdaleansh@gmail.com" target="_blank">
    <img src="https://raw.githubusercontent.com/maurodesouza/profile-readme-generator/master/src/assets/icons/social/gmail/default.svg" width="53" height="40" alt="gmail logo"  />
  </a>
</div>
name: Generate snake animation

on:
  schedule:
    - cron: "0 */12 * * *"  # every 12 hours
  workflow_dispatch:
  push:
    branches:
      - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: Checkout repository
        uses: actions/checkout@v3

      - name: Generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          palette: github-dark

      - name: Push snake.svg to output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: .   # push from current folder (where snake.svg is)
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}

###
