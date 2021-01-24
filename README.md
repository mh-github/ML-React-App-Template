# ML-React-App
It's a template on which we can build a React app and call endpoints to make predictions.

### Usage
The complete guide to use this repository: https://towardsdatascience.com/create-a-complete-machine-learning-web-application-using-react-and-flask-859340bddb33

----------------------------------------------------------------------------------

The example use case is iris flowers prediction. To run it, clone the repository and open two terminals. In both of them, cd into example/iris-data-classifier/ML-React-App-Template and run the following commands:\
Terminal 1
```
$ cd ui
$ yarn install
$ sudo npm install -g serve
$ npm run build
$ serve -s build -l 3000
```

Terminal 2
```
$ cd service
$ FLASK_APP=app.py flask run
```

The run command throws an error:\
from werkzeug import cached_property\
Import_Error : cannot import name 'cached_property'

To fix this error, two changes are required.\
1) requirements.txt\
change `flask-restplus==0.12.1`\
to `flask-restx==0.2.0`

`$ pip3 install -r requirements.txt`

2) app.py\
In the line: `from flask_restplus import Api, Resource, fields`\
change `flask_restplus` to `flask_restx`

After executing the command 'npm run build' in Terminal 1 and starting the servers in both the terminals, you can access the application at\
http://localhost:3000