Heroku makes deployment of arbitrary apps including Panel apps and dashboards very easy and provides a free tier to get you started. This makes it a great starting point for users not too familiar with web development and deployment.

To get started working with Heroku [signup](https://signup.heroku.com) for a free account and [download and install the CLI](https://devcenter.heroku.com/articles/getting-started-with-python#set-up). Once you are set up follow the instructions to log into the CLI.

## Deploying this app

1. Clone this repository

2. Modify the `Procfile` which declares which command Heroku should run to serve the app. In this sample app the following command serves the `iris_kmeans.ipynb` example and the websocket origin should match the name of the app on Heroku `app-name.herokuapp.com` which you will declare in the next step:

```
web: panel serve --address="0.0.0.0" --port=$PORT iris_kmeans.ipynb --allow-websocket-origin=app-name.herokuapp.com
```

4. Create a heroku app using the CLI ensuring that the name matches the URL we declared in the previous step:

```
heroku create app-name
```

5. Push the app to heroku and wait until it is deployed:

```
git push heroku master
```

6. Visit the app at app-name.herokuapp.com


## Modifying the app

In order to serve your own app simply replace the `iris_kmeans.ipynb` with your own Jupyter notebook or Python file declaring a Panel app and then modify the `Procfile` to start that app instead.
