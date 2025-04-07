<div align="center" style="max-width: 900px; margin: 0 auto;">
  <img
    src="https://capsule-render.vercel.app/api?type=wave&color=0:FF4040,100:FF0000&height=180&section=header&animation=fadeIn"
    alt="wave header"
    style="width: 100%;"
  />
</div>

name: GitHub Snake Game

on:
  # Schedule the workflow to run daily at midnight UTC
  schedule:
    - cron: "0 0 * * *"
  # Allow manual triggering of the workflow
  workflow_dispatch:
  # Trigger the workflow on pushes to the main branch
  push:
    branches:
      - main
jobs:
  generate:
    runs-on: ubuntu-latest
    timeout-minutes: 10
    steps:
      # Step 1: Checkout the repository
      - name: Checkout Repository
        uses: actions/checkout@v3
      # Step 2: Generate the snake animations
      - name: Generate GitHub Contributions Snake Animations
        uses: Platane/snk@v3
        with:
          # GitHub username to generate the animation for
          github_user_name: ${{ github.repository_owner }}
          # Define the output files and their configurations
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark
            dist/ocean.gif?color_snake=orange&color_dots=#bfd6f6,#8dbdff,#64a1f4,#4b91f1,#3c7dd9
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
      # Step 3: Deploy the generated files to the 'output' branch
      - name: Deploy to Output Branch
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./dist
          publish_branch: output
          # Optionally, you can set a custom commit message
          commit_message: "Update snake animation [skip ci]"

<div align="center" style="max-width: 900px; margin: 0 auto;">
  <img
    src="https://capsule-render.vercel.app/api?type=wave&height=120&section=footer&animation=fadeIn&color=0:FF4040,100:FF0000"
    alt="wave footer"
    style="width: 100%;"
  />
</div>
