---
layout: post
date: 2024-05-12 22:45:00 +1000
title: 6. Coding Skills Challenge
---

#### Write a program that allows a user to input their coding skills and then tells them:

#### a) Their overall "coding skill score"
#### b) Skills they may want to learn, and how much each one would improve their score
#### c) Points per skill are as follows:
<ul>
 <li>Python (1)</li>
 <li>Ruby (2)</li>
 <li>Bash (4)</li>
 <li>Git (8)</li>
 <li>HTML (16)</li>
 <li>TDD (32)</li>
 <li>CSS (64)</li>
 <li>JavaScript (128)</li>
</ul>


##### Answer 🙋‍♂️

Below is the code structure for the challenge:

```python
# Assign the weight for each of the coding subjects
def coding_skill_score(skills):
  skills_weight = {'Python': 1,'Ruby': 2,'Bash': 4,'Git': 8,'HTML': 16,'TDD': 32,'CSS': 64,'JavaScript': 128}

# Initializing 2 variables for total score and the recommended skills
  total_coding_score = 0
  learn_skills = {}

# Calculating the coding skill score
  for skill, value in skills.items():
      if value.lower() == 'yes':
          total_coding_score = total_coding_score + skills_weight[skill]
      else:
          learn_skills[skill] = skills_weight[skill]

  return total_coding_score, learn_skills

# Collect the user input for each coding subject 
def main():
  skills = {
      'Python': input("1. Python: "),
      'Ruby': input("2. Ruby: "),
      'Bash': input("3. Bash: "),
      'Git': input("4. Git: "),
      'HTML': input("5. HTML: "),
      'TDD': input("6. TDD: "),
      'CSS': input("7. CSS: "),
      'JavaScript': input("8. JavaScript?: ")
  }

  total_coding_score, learn_skills = coding_skill_score(skills)

# System output of the total score
  print(f"\nYour current coding skill score is: {total_coding_score}")

# System recommendation for new skills to user
  if learn_skills:
      print("\nWe recommend you learn the following skills and get additional points:")
      for skill, points in learn_skills.items():
          print(f"{skill}: {points} points")
  else:
    print("\nYou have 100% of the skills we are looking for!!")

# Introduction to the candidate before questions
if __name__ == "__main__":
  print("Hi! Thank you for applying to ACME Corporation!")
  candidate_name = input("What is your name: ")
  print("Thank you,", candidate_name,"!")
  print("This is our coding skills questionnaire for the role you applied!")
  print("Do you have coding skills for the below (yes/no)?")

# Begin the questions
  main()

# Final statement after recommendations
  print("\nAll the best!")
```
### ANSWER

When the program is run, the below output is generated: 

**(1) When new skills are required:**

```
Hi! Thank you for applying to ACME Corporation!
What is your name: Manoj
Thank you, Manoj !
This is our coding skills questionnaire for the role you applied!
Do you have coding skills for the below (yes/no)?
1. Python: yes
2. Ruby: no
3. Bash: no
4. Git: yes
5. HTML: yes
6. TDD: no
7. CSS: yes
8. JavaScript?: no

Your current coding skill score is: 89

We recommend you learn the following skills and get additional points:
Ruby: 2 points
Bash: 4 points
TDD: 32 points
JavaScript: 128 points

All the best!
```
**(2) When all skills are available**
```
Hi! Thank you for applying to ACME Corporation!
What is your name: Manoj
Thank you, Manoj !
This is our coding skills questionnaire for the role you applied!
Do you have coding skills for the below (yes/no)?
1. Python: yes
2. Ruby: yes
3. Bash: yes
4. Git: yes
5. HTML: yes
6. TDD: yes
7. CSS: yes
8. JavaScript?: yes

Your current coding skill score is: 255

You have 100% of the skills we are looking for!!

All the best!
```
