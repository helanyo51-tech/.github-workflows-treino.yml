# .github-workflows-treino.yml
name: Treino do dia
on:
  schedule:
    - cron: "0 9 * * *"
  workflow_dispatch:
jobs:
  treino:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-java@v4
        with:
          distribution: temurin
          java-version: "21"
      - run: mvn -q compile exec:java -Dexec.mainClass=App
