# gpt3-chatbot

import openai

openai.api_key = "kendi keyini yapıştır"

def generate_answer(question):
    response = openai.Completion.create(
        engine="text-davinci-002",
        prompt=question,
        max_tokens=1024,
        n=1,
        stop=None,
        temperature=0.5,
    )
    answer = response["choices"][0]["text"].strip()
    return answer


while True:
    question = input("You: ")
    answer = generate_answer(question)
    print("Bot: ", answer)

