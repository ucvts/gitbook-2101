# Collecting

## Collection Methods

Before we can store and process data or glean any insights from it, we need to gather this data into one place. This is a monumental effort, which involves digital and analog methods.

{% embed url="https://www.youtube.com/watch?v=KX0KqHF\_njI&list=PLUEYQSaHI9SKkvRjT-z1rbLI\_wLo-oMtu" %}

We collect data using a variety of methods, some digital and others not.

* Surveys
* Sensors
* Transactional data \(such as from credit cards\)
* Websites storing information about users \(and their behaviors\)
* Crowdsourcing data

This data is then stored in a variety of places. This can be a personal hard drive, a USB stick, or a CD or DVD. More commonly, though, it's a vast network of database servers.

## Data Access

Once all that data is stored in a database, we need ways to access it. There are a few strategies.

* Database queries
* API calls

To interact with databases, we can use various dialects of SQL \(which stands for Structured Query Language\) to communicate requests. The database, in turn, send us the data we request.

Likewise, an API \(which stands for application programming interface\) allows developer to request data from a networked endpoint. Essentially, an application can make an HTTP request to known server endpoints. The endpoint, which is probably backed by a database, grabs the requested information and sends it back to the application.

### Usable Data

If we want to visualize data, we need to make sure it's usable. This depends on the type of data we're working with, but the process can be generalized.

Data sanitization \(or cleaning the data\) ensures that data is the format you expect and need. If something doesn't fit the desired format, it can be rejected. The manner in which data is collected can have a lot to do with making sure the data is clean.

A survey asking students to choose their eye color is more reliable than having an assistant view pictures and writing down the colors of their eyes. This can get out ahead of some of the data sanitization issues. A multiple-choice format prevents responders from entering information that isn't an eye color.

