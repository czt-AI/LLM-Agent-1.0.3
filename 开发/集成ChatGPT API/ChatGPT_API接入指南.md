import requests

def chatgpt_api(prompt, max_tokens=60, temperature=0.7, top_p=1.0, frequency_penalty=0.5, presence_penalty=0.5):
    url = "https://api.openai.com/v1/engines/davinci-codex/completions"
    headers = {
        "Authorization": "Bearer YOUR_API_KEY",
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
    response = requests.post(url, headers=headers, json=data)
    return response.json()

# 使用示例
response = chatgpt_api("Translate the following English text to French: Hello, how are you?")
print(response)