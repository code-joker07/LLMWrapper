# LLMWrapper
Class Definition: LLMWrapper:
The main logic of the script is contained within this class. It wraps around OpenAI's API to facilitate interaction with the LLM.

**Class Variables**:

**MAX_TOKENS**: The maximum number of tokens that can be sent in a single request.
**RATE_LIMIT_SLEEP_DURATION**: Time (in seconds) the script should wait if the API rate limit is exceeded.
**Initialization (__init__ method)**:
This method initializes an empty conversation history and an empty current prompt.

**call_llm_api Method**:
This method sends a request to the LLM using OpenAI's API with the given text and conversation history. If the text is too long, it raises an error.

**format_prompt Method**:
This formats the current prompt into a semicolon-separated string.

**update_prompt_variables Method**:
This method updates the current prompt with new variables provided.

**add_to_history Method**:
After getting a response from the LLM, this method adds the user input, LLM's response, and the current prompt to the conversation history.

**get_formatted_conversation Method**:
Returns the entire conversation history formatted as strings.

**Error Handling Methods**:
There are methods to handle two specific types of errors:

**handle_rate_limit_error**: Handles API rate limit errors by waiting for a certain duration.
handle_token_limit_error: Handles token limit errors by removing the oldest conversation entries until the total number of tokens is under the limit.
**send_to_llm Method**:
This is the main method to send user input to the LLM. It updates the current prompt, ensures the conversation doesn't exceed the token limit, sends the request, and adds the response to the history.

**Usage**:
This section of the code provides an interactive loop for the user to input text and get a response from the LLM. The loop continues until the user types "exit".

wrapper = LLMWrapper(): An instance of the LLMWrapper class is created.
while True: This starts an infinite loop where the user is prompted for input. If the user types "**exit**", the loop breaks.
