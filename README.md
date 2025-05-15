# template.neo.cicd
template.neo.cicd

jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3

      - name: Запуск моего CICD шаблона
        uses: <username>/template.neo.cicd/.github/actions/deploy@main
        # если action лежит в другом репозитории
        # указать username и репо, потом путь к action и ветку или тег
        # например: uses: anvarjn/template.neo.cicd/.github/actions/deploy@main
        # secrets и env передаются через with и env, если нужно
        env:
          DOCKERHUB_USERNAME: ${{ secrets.DOCKERHUB_USERNAME }}
          DOCKERHUB_TOKEN: ${{ secrets.DOCKERHUB_TOKEN }}
