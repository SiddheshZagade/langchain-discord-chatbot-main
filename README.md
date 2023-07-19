# GPT-3.5 LangChain Discord Chatbot

This is a Discord chatbot that integrates OpenAI's GPT-3.5 turbo model and LangChain to generate responses to user messages. The chatbot application is designed to process user inputs, generate responses using the GPT-3.5 model, and manage user data and conversation history with LangChain. The memory of the chatbot persists in MongoDB.

## Installation

1. Ensure Python is installed on your machine.
2. Clone the repository to your local machine.
3. It's recommended to create a virtual environment to isolate the dependencies for this project. You can do this using `virtualenv`:
   bash
   # Install virtualenv
   pip install virtualenv

   # Create a virtual environment
   virtualenv --python=python3 venv

   # Activate the virtual environment
   source venv/bin/activate
   
4. Install the required packages using `pip install -r requirements.txt`.
5. Set the necessary environment variables in the `.env` file:
   - `OPENAI_API_KEY`: Your OpenAI API key.
   - `MONGODB_URI`: Your MongoDB Connection URI.
   - `MONGODB_DB_NAME`: Your MongoDB Database Name.
   - `DISCORD_API_KEY`: Your Discord API token.
   - `FLASK_PORT`: Flask Port, default is 5000.
6. Run the Flask server using `python app.py`.
7. Run the Discord bot using `python main.py`.

## Usage

To use the bot, send a message in a Discord channel that the bot has access to. The bot will respond with a message generated by the GPT-3.5 language model.

To send a private message to the bot, start your message with a question mark (`?`). For example, to send a message to the bot saying "Hello", send the message `?Hello`.

The application runs a web server that listens for HTTP POST requests on the `/process` endpoint. The POST request should contain a JSON object with the following properties:

- `username`: The username of the user.
- `message_input`: The message input from the user.
- `input_type`: The type of the input. Currently, only 'text' input type is supported.

The application responds with a JSON object that contains the chatbot's response to the user's input.

## Structure

The application is structured into six main Python files:

1. `app.py`: This is the main Flask application file. It sets up the Flask application and defines the routes for the application.
2. `Chatbot.py`: This file defines the Chatbot class. The Chatbot class connects to a MongoDB database and provides methods for managing users.
3. `User.py`: This file defines the User class. The User class represents a user of the chatbot and provides methods for generating responses to user's questions.
4. `memory.py`: This file provides functions for managing a user's conversation history.
5. `config.py`: This file provides functions for setting up logging and retrieving environment variables.
6. `discord_bot.py`: This file contains the Discord bot functionality, including processing and sending messages.

## Contributing

Contributions are welcome. Please submit a pull request if you want to propose changes.

## Support

If you encounter any issues or have any questions, please open an issue on GitHub.


## License

This project is licensed under the terms of the MIT license.