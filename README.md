Here's the updated documentation with your requested section added **after "2. Via Function Calls in Your Project"** while keeping the rest of the document unchanged.

---

```markdown
# ChatGPT Unofficial API Selenium

## ⭐ Video

**Link** – [https://youtu.be/cMCn2cljlls](https://youtu.be/cMCn2cljlls)

## ⭐ Why this API?

This is an unofficial API for ChatGPT using Selenium. It is not recommended to use this API for production. This API is only for testing purposes.

It is designed for projects that need to use the ChatGPT API for testing without incurring the cost of the official API.

> **Note:** This API is significantly slower than the official API, so it is not recommended for production use.

## ⭐ File Structure

### 1. Chromedriver Handler

- **chrome_d_download.py** – Used to download the Chrome driver.
- **unzipper.py** – Used to unzip the Chrome driver.

### 2. Remote Chrome Browser Handler

- **chrome_handler.py** – Used to handle the remote Chrome browser.

### 3. ChatGPT & Core Functions Handler

- **api_backend.py** – Manages interactions with ChatGPT via Selenium.
- **helper_funcs.py** – Contains helper functions for Selenium operations.

## ⭐ Installation

### 1. Create and Activate a Virtual Environment

#### For Linux

```bash
python3 -m venv venv
source venv/bin/activate
```

#### For Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### 2. Install Requirements

```bash
pip install -r req.txt
```

### 3. Download Chrome Driver

(This will automatically download the Chrome driver for your OS.)

```bash
python chrome_d_download.py
```

## ⭐ Logging in to ChatGPT with Remote Chrome Browser

### 1. Start the Remote Chrome Browser

```bash
python chrome_handler.py s
```

> Now you will see a Chrome browser window opened. Use this browser to log in to ChatGPT and accept the permission prompts on the ChatGPT page.  
> Visit [https://chat.openai.com/chat](https://chat.openai.com/chat), paste the link into the remote Chrome browser, and log in.

### 2. Close the Remote Chrome Browser

```bash
python chrome_handler.py k
```

## ⭐ Using the API

### 1. Directly via Terminal

```bash
python api_backend.py
```

This will open an interactive terminal where you can type your message and receive responses from ChatGPT.  
To exit the program, type `!quit` and press Enter.

### 2. Via Function Calls in Your Project

```python
import api_backend

# Start the remote Chrome browser and navigate to ChatGPT. (Call only once)
api_backend.start_chat_gpt()

# Send a prompt and store the response in a variable. (Call as many times as needed)
variable = api_backend.make_gpt_request("what is gpt model?")

# Close the remote Chrome browser. (Call only once)
api_backend.stop_chat_gpt()
```

### 3. Using the API for Document Inference (e.g., PDF Text Files)

```python
import api_backend

# Step 1: Start the remote Chrome browser and navigate to ChatGPT.
api_backend.start_chat_gpt()

# Step 2: Upload your file once.
pdf_path = input("Enter the full path to your PDF file: ")
upload_status = api_backend.upload_file(pdf_path)
print(upload_status)  # Displays a success or error message.

# Step 3: Send your prompt (the file remains in context).
response = api_backend.make_gpt_request("what is gpt model?")
print("Response:", response)

# You can send more prompts as needed:
another_response = api_backend.make_gpt_request("explain the GPT-4 architecture")
print("Response:", another_response)

# Step 4: Stop the remote Chrome browser.
api_backend.stop_chat_gpt()
```

> **Note:** You can also run the `testing_api.py` file to see an example of how to use the API in your project.

## ⭐ Extras

- In the `start_chat_gpt` function of the `api_backend.py` file, the `gmail_xpath` is used to search by the email holder's name. You can change this to the user's name to enable auto-login to ChatGPT if the user is already logged in to Google in the remote Chrome browser.

## ⭐ Improvements

- The `make_gpt_request()` function should be improved to handle errors.
- The response from `make_gpt_request()` should be returned in a well-formatted JSON format.
- Instead of using `time.sleep()`, the code should rely on Selenium's implicit and explicit waits.
- Consider using threading to enable the API to be used in multiple projects simultaneously.
- The speed of the API should be improved. For instance, you could use the `requests` module or `asyncio` to enhance performance.

## ⭐ License

This project is licensed under the MIT License – see the [LICENSE](LICENSE) file for details.

## ⭐ Contributing

Contributions are welcome!  
If you would like to contribute, please fork this repository and submit a pull request. Contributions in the form of code improvements, bug fixes, or new features are all appreciated.

Thank you.

## Star History

<a href="https://star-history.com/#Priyanshu-hawk/ChatGPT-unofficial-api-selenium&Date">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://api.star-history.com/svg?repos=Priyanshu-hawk/ChatGPT-unofficial-api-selenium&type=Date&theme=dark" />
    <source media="(prefers-color-scheme: light)" srcset="https://api.star-history.com/svg?repos=Priyanshu-hawk/ChatGPT-unofficial-api-selenium&type=Date" />
    <img alt="Star History Chart" src="https://api.star-history.com/svg?repos=Priyanshu-hawk/ChatGPT-unofficial-api-selenium&type=Date" />
  </picture>
</a>
```

