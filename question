#!/usr/bin/env python3

import os
import sys
import openai
import logging
from rich.markdown import Markdown
from rich import print as rprint
from halo import Halo

# Setup logging based on environment variable
log_level = os.environ.get("LOG_LEVEL", "WARNING").upper()
logging.basicConfig(level=getattr(logging, log_level))

# Read OpenAI API key from environment variable
api_key = os.environ.get("OPENAI_API_KEY")
if not api_key:
    logging.error("OPENAI_API_KEY environment variable not set.")
    exit(1)

openai.api_key = api_key

def call_openai_api(question):
    try:
        MODEL = "gpt-4-0613"
        messages = [{"role": "user", "content": question}]
        
        # Make API call
        with Halo(text='Waiting for response...', spinner='dots'):
            response = openai.ChatCompletion.create(
                model=MODEL,
                messages=messages,
                temperature=0,
            )
        return response['choices'][0]['message']['content']
    except Exception as e:
        logging.error(f"API call failed: {e}")
        return None

if __name__ == "__main__":
    if len(sys.argv) < 2:
        logging.error("No query string provided.")
        exit(1)

    # Get user input from command line argument
    question = sys.argv[1]
    logging.info(f"Received input: {question}")

    # Call OpenAI API
    response = call_openai_api(question)

    # Output response or failure message
    if response:
        markdown_response = Markdown(response)
        rprint("Assistant says:", markdown_response)
    else:
        print("Failed to get a response.")

