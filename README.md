# Predictive Maintenance IoT

## What's this all about?

This project is my attempt to catch machine failures BEFORE they happen, using real‑time IoT sensor data. By keeping an eye on temperature, vibration, and pressure, we're building a model that can say, "Hey, something's not right here" ideally with enough time to actually do something about it and to avoid all kind of failures. 

## How the pipeline flows

Instead of a chaotic pile of scripts, we're building a clean, modular pipeline. Data goes in one end, predictions come out the other. It looks kinda like this:

**Raw Sensor Data** → **EDA & Cleaning** → **Feature Engineering**  
→ **Sequence Generation** → **LSTM Training** → **Validation**  
→ **FastAPI Service** → **Docker Container** → **Ready for production!**

This step‑by‑step flow keeps things debug‑friendly and makes it dead simple to swap out models or tweak parameters later on. Plus, when we eventually scale up to massive datasets, the pipeline stays the same we just feed it more data.

## The Data

We're working with 10,000 sensor readings, each one capturing a moment in the life of an industrial machine. Here's what we're looking at:

- **Time** –> when the reading was taken
- **Temperature**, **Vibration**, and **Pressure** –> the vital signs of our equipment
- **Failure_warning** –> a heads‑up that trouble might be brewing
- **Failure** –> the hard truth: did it actually break down?

Of course, for real-world industrial projects we'd scale this up to much larger datasets without breaking a sweat. But right now, we're in the fast‑iteration phase keeping the dataset manageable lets us test ideas, tweak features, and validate our pipeline quickly before we go big.


## Where we're at right now

- The project skeleton is up and running 
- A clean virtual environment keeps our dependencies happy and isolated  
- We've already poked around the data with some initial EDA – got a feel for distributions, spotted a few outliers, and started forming some hypotheses  

## What's coming next

- **Feature engineering** –> crafting rolling windows, lagged variables, and other domain‑inspired goodies to give the model more context  
- **Sequence generation** –> turning our time‑series into LSTM‑friendly chunks  
- **Training the LSTM** –> fingers crossed! Lots of tuning and experimenting ahead  
- **Building a FastAPI endpoint** –> so we can actually serve predictions via a simple REST API  
- **Dockerizing the whole thing** –> because reproducibility matters, and nobody likes "it works on my machine"  

