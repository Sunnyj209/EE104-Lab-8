# EE104-Lab-8

Video demonstration
Lab 8 part 1 - https://youtu.be/bPzUg8eCXJk
Lab 8 part 2 - https://youtu.be/OkTbufrim4Y


Reference github files
https://github.com/openai/openai-cookbook.git


for this code to work you can go to my github and copy my folder into the the reference github folder. I split it this way
because the files are to big to compress without degrading the quality


-----KRIA TRAFFIC CONTROLLER-----

Sure! Here's an example README file based on the code you provided:

# Traffic Light and Pedestrian Crossing Controller

This is a Python program that controls a traffic light and pedestrian crossing using a Raspberry Pi or similar device with GPIO pins.

## Requirements

- Python 3
- RPi.GPIO library

## Installation

1. Install Python 3 on your Raspberry Pi if it's not already installed.
2. Install the RPi.GPIO library by running the command `pip3 install RPi.GPIO` in your terminal.

## Usage

1. Connect the traffic light and pedestrian crossing LEDs to the GPIO pins of your Raspberry Pi according to the pin numbers specified in the code.
2. Run the program using the command `python3 traffic_light.py` in your terminal.
3. The traffic light and pedestrian crossing will turn on and off in sequence according to the code.
4. The program will enter an infinite loop after the initial sequence, keeping the lights and counter in their final state until the program is stopped or the device is turned off.

## License

This program is licensed under the MIT License. See the LICENSE file for more information.

## Contributing

Pull requests and bug reports are welcome! Please create an issue first to discuss any major changes or additions.

--------------code used---------------
short_delay = 0.5
delay = 2
counter_delay = 9
green_traffic = 0
yellow_traffic = 1
red_traffic = 2
green_pedastrain = 4
red_pedastrian = 5
counter = 3

green_traffic = GPIO(GPIO.get_gpio_pin(green_traffic), 'out')   # initialize green traffic light pin as input
yellow_traffic = GPIO(GPIO.get_gpio_pin(yellow_traffic), 'out')         # initialize LED pin as output
red_traffic = GPIO(GPIO.get_gpio_pin(red_traffic), 'out')  # initialize slider LED pin as output
green_pedastrain = GPIO(GPIO.get_gpio_pin(green_pedastrain), 'out')   # initialize green traffic light pin as input
red_pedastrian = GPIO(GPIO.get_gpio_pin(red_pedastrian), 'out')  # initialize slider LED pin as output
counter = GPIO(GPIO.get_gpio_pin(counter), 'out')  # initialize slider LED pin as output

green_traffic.write(1)       # turn on green light
sleep(delay)                 # wait for delay seconds
green_traffic.write(0)       # turn off green light
yellow_traffic.write(1)      # turn on yellow light
sleep(delay)                 # wait for delay seconds
yellow_traffic.write(0)      # turn off yellow light
red_traffic.write(1)         # turn on red light
green_pedastrain.write(1)    # turn on green pedastrian light
sleep(counter_delay)         # wait for delay seconds
green_pedastrain.write(0)    # turn on green pedastrian light
sleep(delay)
red_pedastrian.write(1)      # turn on red pedastrian light
sleep(delay)
counter.write(0)             # turn on pedastrian counter
green_traffic.write(1)       # turn on green light
red_traffic.write(0)         # turn on red light

while True:              # loop indefinitely
    pass                 # do nothing, LEDs stay ON


----- Q and A -----

# File Q&A with Next.js and Flask

File Q&A is a web app that lets you find answers in your files. You can upload files and ask questions related to their content, and the app will use embeddings and GPT to generate answers from the most relevant files. \

## Requirements

To run the app, you need:

- An OpenAI API key. You can create a new API key [here](https://beta.openai.com/account/api-keys).
- A Pinecone API key and index name. You can create a new account and index [here](https://www.pinecone.io/).
- Python 3.7 or higher and pipenv for the Flask server.
- Node.js and npm for the Next.js client.

## Set-Up and Development

### Server

Fill out the config.yaml file with your Pinecone API key, index name and environment.

Run the Flask server:

```
cd server
bash script/start "<your OPENAI_API_KEY>"
```

### Client

Navigate to the client directory and install Node dependencies:

```
cd client
npm install
```

Run the Next.js client:

```
cd client
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the app.

## Limitations

The app may sometimes generate answers that are not in the files, or hallucinate about the existence of files that are not uploaded.

OPENAI_API_KEY = ""
YOUR OPENAI ORG KEY = ""
PINECONE_API_KEY=""
PINECONE_ENV=""

Need to make an account at openai and register for an api key
also need to make account at pinecone ai so you can get an api key and enviroment


------------ web crawl ------------

Sure, here's a README file for the code:

Web Scraping and OpenAI API Demo
This is a Python program that scrapes text from a website and uses the OpenAI API to answer questions about the text. It includes the following steps:

Import necessary modules
Define switches and variables
Create a class to parse HTML and get hyperlinks
Function to get hyperlinks from a URL within the same domain
Function to crawl a website and save text files
Function to remove newlines from text
Load tokenizer and create a histogram of the number of tokens per row
Split the text into chunks of a maximum number of tokens
Create a new histogram of the number of tokens per row after splitting
Get embeddings for each chunk of text and save to a CSV
Read embeddings from the CSV
Function to create a context and answer a question using the OpenAI API
Example questions and answers
Installation and Setup
Clone the repository or download the code as a zip file
Install the required Python packages by running pip install -r requirements.txt
Create a .env file in the root directory of the project with your OpenAI API key, like so:
makefile
Copy code
OPENAI_API_KEY=<your_api_key>
Run the program using python main.py
Usage
The program will prompt you to enter a question, and then it will use the OpenAI API to try to answer your question based on the text it scraped from the website. You can ask any question that you think the text might be able to answer.

Notes
This program was last trained on knowledge up to September 2021, and it may not be accurate or up to date for certain questions. Additionally, the program may not work if the website's structure or content has changed significantly since the time of scraping. Finally, the program may run into rate limit issues if too many files are embedded at once; please refer to the OpenAI rate limit guide for more information.
