# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) WDSI Hackathon

WDI, meet DSI. DSI, WDI. Let's build some stuff.

## Prompt
You and your team will take a dataset and build an application (or website) that:
- visualizes the data in an interesting way
- prompts the user for inputs and make predictions based on the data using a flask API
- is deployed and publically accessible on AWS

![](.images/image.jpg)

## Schedule
Each team will consist of two DSI students and two WDI students (as best we can divide). First the team will meet this afternoon to select a dataset and plan what they intend to build. The following day, the DSI team will build and deploy a FLASK api on AWS and the day after the WDI students will build a front-end application that utilizes this API to filter & visualize data as well as make predictions via a form. The final day, we will take the morning to see the present the final applications. We know this is a short amount of time, but it should suffice to get a MVP (minimum viable product) up and running.

## Approach
- Whiteboard an outline of what you want the final product will look like. We require a datatable somewhere in the front end that allows for filtering of the data, but the other visualizations are up to you.  If you choose a dataset with map data, perhaps you may want to plot and points observations via `read` endpoint on a map and predict the class or price of a new location the user can click on? If you are consuming time-series data, perhaps you will want to visualize this timeseries, also filtering the date range it via the `read` endpoint and forcast a value some time in the future. Ultimately, this is planning is the most important part of your application, but be sure to communciate this early so that both teams know what json to request and respond with.
- Set up a Git Organization with two repos - one for a Python server and one for a web full-stack app. Agree on a git workflow to share code
- Decide on the tools you want to use. For Python, we recommend Flask. For Web, you've been given several server and front-end technologies, make a choice based on what your group is comfortable with.
- Build out something quick that can connect between the two apps! Start testing locally and then deploy to AWS!

## Tips for DSI Students
- Start by creating dummy outputs so your WDI team members have something to work with and meet the requirements for the API. For example, after reviewing your dataset if your model will output a json object with three key, value pairs, start by building a Flask app that returns a json object of 3 random values to a route - the exact structure of the json returned is up to you and should be communicated maong your team, but specific endpoints are required.
- Building this **minimum viable product** and passing it along to the WDIers with working endpoints will be important even if the model performs poorly. As an example, please review the Flask app in the [my_flask_api](./my_flask_api/) folder and utilize the examples given in from our flask lesson.
- Only once you've built your Flask API and have the required endpoints built, you should **only then** you get more complex (engineer your features, try different models, tune hyperparameters...)
- Discuss with your team the expected json outputs for your endpoints and what input parameters the POST requests will take.
- Do your data cleaning, EDA, and model tuning in a Jupyter notebook. Export the fitted model as a pickled file to save on processing time.
- Deploy on AWS!

## DSI requirements
- Deploy Flask API to AWS
- The Flask API should have the following endpoints:
    1. `predict` route which accepts post request for a single or multiple observations inputed through a form or csv file upload via the front-end that returns json for the predicted results.
    2. `read` route which accepts a get request with parameters
- You are not responsible for developing the templates for the application - the WDI students will build these via an SPA or their choice. the demo form.html and app.py is just there for you to get started testing your endpoints.
- A separate jupyter notebook where you are practicing your modeling before moving it to python file for flask or pickling the model.

#### Bonus:
- Utilize a pickled model file that you have trained locally on your data.
## WDI requirements
- Create a front end application that consumes the DSI team's api.
- Deploy your application using Surge
- Create one visualization that utilizes a POST request (you'll probably want a form) and renders the result of that request.
- Create one visuialization that uses a GET request that retrieves a set of data for another chart.  This GET request may require some filters or queries, coordinate with your group.

## Tips for WDI Students
- You can use any front-end technologies you want here!  React does offer some nice features, so we'd loosely suggest it, but the choice is yours.
- Communicate with your DSI buddies to agree upon how your applications will communicate.  They are building servers and know how to handle both GET and POST requests.  What kind of things can you guys do with that?
- Once you decide on how your apps communicate make some design decisions about what the app will look like and how the data will be visualized.
- Use fetch to make your AJAX calls to the DSI-team's API.
- If you are using React, design your components first and outline their state.  Once a plan is in place assign people to create entire components - this will help avoid git conflicts.  The important part here to make sure that there is clear communication about what is being passed through props to ensure a seamless connection.

## WDI - Helpful Visualization Libraries:
- [ChartKick (React)](https://chartkick.com/react) - Offers line, bar, pie, geo (think a global heatmap).  One-line components, pretty nifty. [npm link](https://www.npmjs.com/package/react-chartkick)
- [Chart.js](https://www.chartjs.org/) - Very popular simple charts library. Clean look, pretty animations. [npm link](https://www.npmjs.com/package/react-chartjs-2)
- [Canvas JS](https://canvasjs.com/react-charts/) - pretty, lots of chart options.
- [React Google Charts](https://react-google-charts.com/) - Robust charting app; Creates charts like the ones seen in Google Sheets. Lots of options.  [npm link](https://www.npmjs.com/package/react-google-charts)
- [Fusion Charts](https://www.fusioncharts.com/react-charts) - One of the most beautiful libraries, limited options but gorgeous if you only need Pie, Line, Bar chart, or other basics.
- [Recharts](http://recharts.org/en-US) - D3 based charting library - [npm link](https://www.npmjs.com/package/recharts)
- [D3](https://d3js.org/) - Considered the king of kings for charting libraries.  This is a vanilla JS library!  There are some React ports of it, but they are largely unsupported.  It's recommended to use the vanilla JS version.

# Datasets to choose from:
Some of these datasets will require merging multiple csvs together.

1. [Taxi Trips in NYC](http://www.nyc.gov/html/tlc/html/about/trip_record_data.shtml)
2. [MTA's subway turnstile data](http://web.mta.info/developers/turnstile.html)
3. [AirBnB data](http://insideairbnb.com/get-the-data.html)
4. [Uber Trips](https://github.com/fivethirtyeight/uber-tlc-foil-response)
5. [CLEAN DATASETS (image, music, text, etc..)](http://deeplearning.net/datasets/)
6. Find your own. [SUGGESTIONS](https://github.com/bulutyazilim/awesome-datascience#data-sets)
