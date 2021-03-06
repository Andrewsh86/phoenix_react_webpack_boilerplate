# Phoenix React Webpack Boilerplate!
Because new.

## Features
- Phoenix 1.3
- React
- Webpack (with hot reloading)
- SASS

Note: Phoenix 1.3 uses `phx` instead of `phoenix` for things like mix tasks
(`mix phx.server`, for example). Using `phoenix` should still work, but I advice you
to [install Phoenix 1.3](https://github.com/phoenixframework/phoenix/blob/master/installer/README.md)

## Make it your own
```bash
# clone repo with your app name
git clone https://github.com/MainShayne233/phoenix_react_webpack_boilerplate.git your_app_name
# enter project directory
cd your_app_name
# fetch dependencies
mix deps.get
# run handy dandy mix task
mix app.setup YourAppName your_app_name
# create your database
mix ecto.create
# start the server
iex -S mix phx.server
```
Then visit [localhost:4000](http://localhost:4000)

## Compiling assets
This boilerplate serves up assets via the Webpack server middleware. However,
compiling assets is as easy as
```bash
mix assets.digest

# and for prod

MIX_ENV=prod mix assets.digest
```

## Silence the webpack log
The webpack log can be useful when debugging things like a stylesheet synatx error, but it can
be annoying when all you care about is the Elixir console. To silence the webpack server, add ```quiet: true``` to the ```devServer``` config in ```./assets/webpack.config.js```
```javascript
  devServer: {
    hot: true,
    overlay: true,
    quiet: true,
    port: 4002,
    historyApiFallback: true,
    headers: {
      'Access-Control-Allow-Origin': '*',
      'Access-Control-Allow-Methods': 'GET, POST, PUT, DELETE, PATCH, OPTIONS',
      'Access-Control-Allow-Headers': 'X-Requested-With, content-type, Authorization'
    },
  },
```
