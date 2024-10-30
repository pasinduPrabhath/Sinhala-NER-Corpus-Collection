# Contributing Guidelines

Welcome to the Sinhala NER Dataset repository! We're excited to have you contribute to our project focused on Named Entity Recognition for the Sinhala language.

## About this Repository

The purpose of this repository is to create an annotated corpus of Sinhala news articles for Named Entity Recognition (NER) tasks. The dataset currently contains articles from BBC Sinhala and other media sources.

## How to Contribute

1. Star the repository
2. Fork the repository
3. Make your changes
4. Submit a pull request

## 1. Star the Repository
Click on the **Star** button in the top right corner of the repository.

## 2. Forking the Repository
- Click the Fork button on the repository's GitHub page
- Clone your fork locally:
```bash
git clone https://github.com/[YOUR_USERNAME]/sinhala-ner-dataset.git
```

- Create a branch:
``` bash
git checkout -b feature/your-feature-name
```

# Making Your Changes
Entity Types
- Your task is to identify named entities in Sinhala text.
- The supported entity types are:
   # Basic Entities
    - PERSON: Names of individuals
    - LOCATION: Geographic locations, cities, countries
    - ORGANIZATION: Companies, institutions, organizations
    - DATE: Calendar dates, years
    - TIME: Time expressions
  # Hierarchical Event Entities
    - EVENT
      - POLITICALEVENT: Elections, political meetings
      - SPORTSEVENT: Sports matches, tournaments
      - ECONOMICEVENT: Financial events, market changes
      - CULTURALEVENT: Festivals, celebrations

# Steps to Contribute

- Find an object (a sentence or paragraph) that has not been annotated yet or has incomplete annotations.
- Identify Named Entities:
  - For each word or phrase in the text, determine if it belongs to one of the specified named entity categories (e.g., PERSON, LOCATION).
  - If a word does not correspond to any of these named entities, simply remove it from the annotation array.
- Format Annotations:
  - For each identified named entity, create an array with the following information:
    - Starting index of the entity in the text.
    - Ending index of the entity in the text.
    - Named Entity type (e.g., LOCATION, PERSON).
- Output Structure:
The final output should be a JSON object where each text entry is paired with its corresponding entities in this format:
```json
[
    "Your Sinhala sentence here.",
    {
      "entities": [
        [start_index, end_index, "ENTITY_TYPE"]
      ]
    }
]
```

# Example
- Before Annotation:
```json
[
    "සිංහල සිනමා වංශකතාවට නොමැකෙන මතක සටහන් එක් කළ, අමරසිරි කලංසූරිය මහා රංගවේදියා සිය දිවි සැරිය පසුගිය දානිමා කළා.",
    {
      "entities": [
        ["සිංහල", 0, 5, ""],
        ["සිනමා", 6, 11, ""],
        ["වංශකතාවට", 12, 20, ""],
        ["නොමැකෙන", 21, 28, ""],
        ["මතක", 29, 32, ""],
        ["සටහන්", 33, 38, ""],
        ["එක්", 39, 42, ""],
        ["කළ,", 43, 46, ""],
        ["අමරසිරි", 47, 54, ""],
        ["කලංසූරිය", 55, 63, ""],
        ["මහා", 64, 67, ""],
        ["රංගවේදියා", 68, 77, ""],
        ["සිය", 78, 81, ""],
        ["දිවි", 82, 86, ""],
        ["සැරිය", 87, 92, ""],
        ["පසුගිය", 93, 99, ""],
        ["දානිමා", 100, 106, ""],
        ["කළා.", 107, 111, ""]
      ]
    }
  ]
```

- After Annotation:
```json
[
    "සිංහල සිනමා වංශකතාවට නොමැකෙන මතක සටහන් එක් කළ, අමරසිරි කලංසූරිය මහා රංගවේදියා සිය දිවි සැරිය පසුගිය දානිමා කළා.",
    {
      "entities": [
        [0, 5, "EVENT/CULTURALEVENT"],
        [47, 54, "PERSON"],
        [55, 63, "PERSON"]
      ]
    }
]
```

# Submitting Your Changes
- Commit Your Changes:
  - After annotating an object and saving your changes to sinhala_annotation.json, commit your changes using Git:
```bash
git add src/data/sinhala_annotation.json
git commit -m 'Added annotations for [sentence summary]'
```

# Push Your Changes:
- Push your changes to your forked repository:
```bash
git push origin branch-name
```

# Create a Pull Request (PR):
- Go to your forked repository on GitHub and click on the “New Pull Request” button. Submit your pull request with a clear description of what you’ve added or modified.
# Wait for Review and Approval:
- The project maintainers will review your pull request and provide feedback if necessary. Once approved and merged into the main repository, your contribution will be part of the dataset!

# Pulling Updates from the Main Repository
- To stay up to date with changes made to the main repository by other contributors:
  - Add the main repository as an upstream remote:
```bash
git remote add upstream https://github.com/pasinduPrabhath/sinhala-ner-dataset.git
```
  - Fetch updates from upstream:
```bash
git fetch upstream
```

  - Merge updates into your local branch:
```bash
git merge upstream/main
```

  - Push updated code to your fork:
```bash
git push origin branch-name
```

- For one pull request, it is enough to add one object to the corpus.
- Make sure to refer to previous examples and correctly identify the named entities.

# Thank you for your contributions!

We appreciate your help in making this repository a valuable resource for the programming community and the Sinhala NLP developing community.
