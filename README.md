# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

- [ ] Describe the game's purpose.
The game's purpose is to have the player guess a secret number with a limited number of attempts. The game grants hints and tracks score based on correct/wrong inputs.
- [ ] Detail which bugs you found.
There were hints that showed misleading information such as telling the user to go lower instead of actually higher. Wrong answers may sometimes grant points instead of deducting.
- [ ] Explain what fixes you applied.
I was able to fix the bug where hints compared the secret and the user input alphabetically than numerically. I also fixed the score logic to deduct 5 points for wrong inputs and changed the hint messages to show correctly.

## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. User will select Normal difficulty, range of 1-100
2. User guesses 53, returns "Go Lower" (secret is below 53)
3. User guesses 5, returns "Go Higher" (secret is above 5)
4. User guesses 6, returns "Go Higher" (secret is above 6)
5. User guesses 52, returns "Correct" (final score is shown and game ends)

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->

## 🧪 Test Results

```
================= test session starts ==================
platform darwin -- Python 3.14.0, pytest-9.1.0, pluggy-1.6.0
rootdir: /Users/jason/Desktop/ai110-module1show-gameglitchinvestigator-starter
plugins: anyio-4.13.0
collected 3 items                                      
tests/test_game_logic.py ...                     [100%]
================== 3 passed in 0.02s ===================
```

## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
