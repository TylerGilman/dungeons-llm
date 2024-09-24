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
Here is a example prompt we would feed it. Need to manufacture data, but quality is much more important than quantity. Only need around 10-20 detailed examples. \
*Main thing is good training data is necessarily for good model.* \
""" 
[GAME STATE] \
{Encoded game state including current location, NPCs, quest progress, etc.} \
[PLAYER ACTIONS] \
Player 1: {Action description} | Roll: {Roll result} \
Player 2: {Action description} | Roll: {Roll result} \
Player 3: {Action description} | Roll: {Roll result} \
Player 4: {Action description} | Roll: {Roll result} \
[DM RESPONSE] \
{Narrative description of the results of player actions, environmental changes, NPC reactions, etc.} \
[UPDATED GAME STATE] \
{Encoded updated game state reflecting changes from player actions and DM response} \
"""
