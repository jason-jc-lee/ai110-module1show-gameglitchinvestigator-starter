# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The game seemed fine with the guesses the first time I ran it.

- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").

The game appeared to not show the correct hints, and also appeared to require multiple presses on "New Game" to show the correct number of sttempts.

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|  40   |  Go LOWER!        |     Go Higher   |        none            |
|  3    |       Go Higher   | Go LOWER!       | none                   |
|  21   |        Go LOWER!  | Go LOWER!       | none

1. Input: New Game resets attempts to 0, though the game counts at 1
Expected Behavior:  Game should count at 0 too so attempts should equal 0 and not 1
Actual: Attempts is equal to 1 at the start
Console output/Error: none

2. Input: Too High outcome gives points
Expected Behavior: Should deduct points by 5
Actual: Increases points by 5
Console output/Error: none

3. Input: Secret may be a string
Expected Behavior: Should be an integer to correctly compare input integers.
Actual: Tries to compare an integer with a string
Console output/Error: none

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
Claude
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
One example of a correct AI suggestion was when the AI found the string vs integer comparison issue. This would lead to the secret to be converted to a string, causing hints to be compared alphabetically. I verified this by looking in app.py and seeing if that code block was flawed.

- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
One misleading example was when the AI told that Hard's range should be 1,200 despite the code never implying this. I checked to see if this range appeared anywhere in the code other than the fact that it should be harder then Normal.

---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

---

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.
