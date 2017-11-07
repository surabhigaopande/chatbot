#This repository contains data for a conversational text chat bot
The service is written using Flask-RESTful and deployed using App Engine on Google Cloud Platform.

Before running or deploying, install the dependencies using pip:
pip install -t lib -r requirements.txt
To run the service locally, you can run
dev_appserver.py .

Then you can test an example request:

curl -X POST http://localhost:8080/quotesearch -H "Content-Type: application/json" -d '{"result": {"action": "get_quote_event", "parameters": {"author": "Grace Hopper", "topic": "technology"}}}' 
Example response:

{"followupEvent": {"data": {"author": "Grace Hopper", "quote": "The application of systems techniques has been successful in scientific and technical applications . . . It meets difficulty when it is applied in social and political situations largely because people are not 'well-behaved' mathematical functions, but can only be represented by statistical approximations, and all of the extremes can and do occur."}, "name": "respond_with_quote"}}

To deploy, run
gcloud app deploy app.yaml

The service has one endpoint '/qrcquotesearch'
