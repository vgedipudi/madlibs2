# madlibs2
import random

def generate_madlib_prompt():
  """
  Generates a random madlib prompt.

  Returns:
    A string containing a random madlib prompt.
  """

  # Get a random madlib prompt from the list of madlib prompts.
  madlib_prompts = [
    "I went to the {adjective} store and bought a {noun}.",
    "I saw a {adjective} {noun} in the {noun}.",
    "I was {verb}ing when I {verb}ed the {noun}.",
  ]

  return random.choice(madlib_prompts)

def fill_in_madlib_prompt(prompt, user_input):
  """
  Fills in a madlib prompt with user input.

  Args:
    prompt: A string containing a madlib prompt.
    user_input: A dictionary containing the user's input.

  Returns:
    A string containing the filled-in madlib prompt.
  """

  # Replace the placeholders in the prompt with the user's input.
  for placeholder, value in user_input.items():
    prompt = prompt.replace(placeholder, value)

  return prompt

def main():
  # Get the user's input.
  user_input = {}
  for placeholder in ["adjective", "noun", "verb"]:
    user_input[placeholder] = input("Enter a {}: ".format(placeholder))

  # Generate a madlib prompt.
  prompt = generate_madlib_prompt()

  # Fill in the madlib prompt with the user's input.
  filled_prompt = fill_in_madlib_prompt(prompt, user_input)

  # Print the filled-in madlib prompt.
  print(filled_prompt)

if __name__ == "__main__":
  main()
