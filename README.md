# AI-Food-Recipe-Generator
AI Food Recipe Generator – A smart web app that generates personalized recipes using AI based on available ingredients and dietary preferences. Built with React, Node.js.


Project Introduction
AI Recipe Generator is a full-stack web application built on the MERN stack (MongoDB, Express, React, Node.js). A user uploads a photo of food or ingredients, and the app detects what’s in the photo, lets the user adjust the ingredient list, optionally filter by dietary preference, and then generates a complete, structured recipe via AI.

Under the hood, two Groq AI services power the application:

Groq Vision (LLaMA 4 Scout) analyzes the uploaded food photo and returns a list of detected ingredients.
Groq Text (LLaMA 3.3 70B) generates full recipes or quick recipe suggestions from those ingredients, with dietary preference applied.
All generated recipes can be saved to MongoDB Atlas, giving users a personal, searchable, filterable recipe book.

There is no authentication in this app — it is a single-user tool focused entirely on the core AI-powered cooking workflow.

Main Functionalities

1. Image-Based Ingredient Detection
The user uploads a photo — of fridge contents, raw ingredients, or even a cooked dish. The backend converts the image to Base64 and sends it to Groq Vision (LLaMA 4 Scout). The model returns a JSON array of ingredient or dish names. The app parses the array and populates the ingredient list.

2. Editable Ingredient List
After detection, the user sees all identified ingredients as removable tags. They can delete any incorrect detection or manually type additional ingredients not caught by the vision model. This keeps the human in control before the recipe is generated.

3. Dietary Preference Filtering
Before generating a recipe, the user can select one dietary filter from eight options: vegan, vegetarian, keto, gluten-free, dairy-free, low-carb, high-protein, or paleo. The selected preference is injected directly into the Groq prompt, ensuring the generated recipe and its tags comply with the constraint.

4. Full Recipe Generation
The backend sends all ingredients (plus the dietary filter if selected) to Groq LLaMA 3.3 70B with a structured JSON prompt. The AI returns a complete recipe object including: title, ingredient list with quantities, numbered step-by-step instructions, full nutritional breakdown (calories, protein, carbs, fat, fiber), servings, prep time, cook time, difficulty, dietary tags, and serving suggestions.

5. Recipe Suggestions (Multi-Option Flow)
Instead of immediately generating a full recipe, the user can request three quick suggestions. The AI returns three lightweight objects — title, one-line description, difficulty, cook time, and dietary tags. The user clicks their preferred suggestion, which then triggers a full recipe generation for that selected title.

6. Save & Manage Recipes
Any generated recipe can be saved to MongoDB with one click. The Saved Recipes page displays all saved recipes in a card grid with search (by title), filter by diet tag, and filter by difficulty level. Clicking a card opens the full recipe detail view. Recipes can be deleted from both the card and the detail page.

