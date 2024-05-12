---
layout: post
date: 2024-05-12 22:35:00 +1000
title: 6. Coding skill score challenge
---


### Challenge: 
Write a program that allows a user to input their skills and then tells them: 
 a) Their overall "coding skill score" 
 b) Skills they may want to learn, and how much each one would improve their score
 c) The skills are weighted as follows:
 - Python (1)
 - Ruby (2)
 - Bash (4)
 - Git (8)
 - HTML (16)
 - TDD (32)
 - CSS (64)
 - JavaScript (128)

```python
def calculate_skill_score(skills):
    skill_points = {
        'Python': 1,
        'Ruby': 2,
        'Bash': 4,
        'Git': 8,
        'HTML': 16,
        'TDD': 32,
        'CSS': 64,
        'JavaScript': 128
    }

    total_score = 0
    recommended_skills = {}

    for skill, value in skills.items():
        if value.lower() == 'yes':
            total_score += skill_points[skill]
        else:
            recommended_skills[skill] = skill_points[skill]

    return total_score, recommended_skills

def main():
    skills = {
        'Python': input("Do you know Python? (yes/no): "),
        'Ruby': input("Do you know Ruby? (yes/no): "),
        'Bash': input("Do you know Bash? (yes/no): "),
        'Git': input("Do you know Git? (yes/no): "),
        'HTML': input("Do you know HTML? (yes/no): "),
        'TDD': input("Do you know TDD? (yes/no): "),
        'CSS': input("Do you know CSS? (yes/no): "),
        'JavaScript': input("Do you know JavaScript? (yes/no): ")
    }

    total_score, recommended_skills = calculate_skill_score(skills)

    print(f"\nYour overall coding skill score is: {total_score}")

    if recommended_skills:
        print("\nSkills you may want to learn and their potential score improvements:")
        for skill, points in recommended_skills.items():
            print(f"{skill}: {points} points")

if __name__ == "__main__":
    print("Welcome to XYZ Corporation's coding skill evaluation!")
    main()

```

## THE OUTPUT

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
