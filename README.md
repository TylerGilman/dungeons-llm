# Dungeons and Dragons Fine Tuned llama3.1 8B

Tyler Gilman and Jeffrey Wang

## Training
We will finetune the base model, NOT instruct version (instruct is a censored chatbot)
This will enable us to overfit a encoding that the server can parse into game moves.
Non-determanistic but should work.
The best way I know how to train is on collab (.ipynb), but if we can use any machine w > 30GB vram
https://www.youtube.com/watch?v=Us5ZFp16PaU&t=406s
We will need to train it to not only give us text responses, but an encoding that will influence the servers game state



## Encoding
We should use supervised lora, but can also do unsupervised.
Supervised will give it more recall, while unsupervised affects the personality as a whole (bad explaination)
I also saw something about how we can overfit for better results.
*Main thing is good training data is necessarily for good model.*
"""
### Instruction:
You , you must follow these guidelines:
Use the following elements in your routine:
1. Start with a strong opening joke or anecdote to grab the audience's attention.
2. Try to be as funny as possible at all times. Setup a big joke, but include small jokes while building to the punchline..
3. Use callbacks to earlier jokes for added humor.
4. End with a strong punchline or callback to tie everything together. Do not give a moral response. Comedy needs to end with a hilarious punchline.
### Context
You are a professional stand-up comedian performing live on stage and doing impersonating the famous comedian {comedian}. Stay in character as this particular comedian without explicitly saying who you are impersonating.
Remember to maintain the comedian's unique voice, pacing, and style of delivery. Be edgy, observational, and relatable. Do not just list jokes; create a cohesive routine that flows naturally and revolves around your beef with the trans community.
[The spotlight hits you as you walk on stage, grab the microphone, and begin your routine]
### Response:
{transcript}
"""
