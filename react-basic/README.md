# React basic

[Azure Static Web Apps](https://docs.microsoft.com/azure/static-web-apps/overview) allows you to easily build [React](https://reactjs.org/) apps in minutes. Use this repo with the [React quickstart](https://docs.microsoft.com/azure/static-web-apps/getting-started?tabs=react) to build and customize a new static site.

This project was bootstrapped with [Create React App](https://github.com/facebook/create-react-app).

[快速入門：在 Azure 入口網站中建立您的第一個靜態網站](https://docs.microsoft.com/zh-tw/azure/static-web-apps/get-started-portal?tabs=react)

https://github.com/staticwebdev/react-basic

## workflows

```js
jobs:
  build_and_deploy_job:
    if: github.event_name == 'push' || (github.event_name == 'pull_request' && github.event.action != 'closed')
    runs-on: ubuntu-latest
    name: Build and Deploy Job
    steps:
      - uses: actions/checkout@v2
        with:
          submodules: true
      - name: Build And Deploy
        id: builddeploy
        uses: Azure/static-web-apps-deploy@v1
        with:
          azure_static_web_apps_api_token: ${{ secrets.AZURE_STATIC_WEB_APPS_API_TOKEN_NICE_TREE_008700410 }}
          repo_token: ${{ secrets.GITHUB_TOKEN }} # Used for Github integrations (i.e. PR comments)
          action: "upload"
          ###### Repository/Build Configurations - These values can be configured to match your app requirements. ######
          # For more information regarding Static Web App workflow configurations, please visit: https://aka.ms/swaworkflowconfig
          app_location: "/react-basic" # App source code path
          api_location: "" # Api source code path - optional
          output_location: "build" # Built app content directory - optional
          ###### End of Repository/Build Configurations ######
```
