def chatgpt_api(prompt, max_tokens=60, temperature=0.7, top_p=1.0, frequency_penalty=0.5, presence_penalty=0.5):
    url = "https://api.openai.com/v1/engines/davinci-codex/completions"
    headers = {
        "Authorization": f"Bearer YOUR_API_KEY",
        "Content-Type": "application/json"
    }
    data = {
        "prompt": prompt,
        "max_tokens": max_tokens,
        "temperature": temperature,
        "top_p": top_p,
        "frequency_penalty": frequency_penalty,
        "presence_penalty": presence_penalty
    }
    try:
        response = requests.post(url, headers=headers, json=data)
        response.raise_for_status()  # Raises an HTTPError if the HTTP request returned an unsuccessful status code
        return response.json()
    except requests.exceptions.HTTPError as http_err:
        print(f"HTTP error occurred: {http_err}")
        # Parse the error message and extract the error code and message
        error_data = response.json()
        error_code = error_data.get('error', {}).get('code', 'Unknown')
        error_message = error_data.get('error', {}).get('message', 'Unknown error')
        print(f"Error code: {error_code}, Error message: {error_message}")
    except Exception as err:
        print(f"An error occurred: {err}")

# Example usage
chatgpt_api("Translate the following English text to French: Hello, how are you?")