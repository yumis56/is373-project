name: Build and Deploy Hexo Blog

on:
  #push:
   # branches: [ main, master ]
  #pull_request:
    #branches: [ main, master ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      #- name: Set up Docker Buildx
      #  uses: docker/setup-buildx-action@v3

      #- name: Build Docker image
      #  run: |
          docker build -t my-hexo-blog ./ --file Dockerfile

      #- name: Run Hexo server
      #  run: |
      #    docker run -d -p 5000:5000 my-hexo-blog


      - name: Build Docker Image
        run: |
          docker build -t hexo-site .

      - name: Run Docker Container
        run: |
          docker run -d -p 5000:5000 hexo-site
