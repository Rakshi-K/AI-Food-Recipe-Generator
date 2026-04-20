# AI-Food-Recipe-Generator
AI Food Recipe Generator – A smart web app that generates personalized recipes using AI based on available ingredients and dietary preferences. Built with React, Node.js.


Project Introduction
AI Recipe Generator is a full-stack web application built on the MERN stack (MongoDB, Express, React, Node.js). A user uploads a photo of food or ingredients, and the app detects what’s in the photo, lets the user adjust the ingredient list, optionally filter by dietary preference, and then generates a complete, structured recipe via AI.

Under the hood, two Groq AI services power the application:

Groq Vision (LLaMA 4 Scout) analyzes the uploaded food photo and returns a list of detected ingredients.
Groq Text (LLaMA 3.3 70B) generates full recipes or quick recipe suggestions from those ingredients, with dietary preference applied.
All generated recipes can be saved to MongoDB Atlas, giving users a personal, searchable, filterable recipe book.

There is no authentication in this app — it is a single-user tool focused entirely on the core AI-powered cooking workflow.

Problem Identification

Subtitle: The Current Problem in Home Cooking

Every day, millions of people open their fridge, stare at random ingredients, and have no idea what to cook. The existing support system for home cooks is fundamentally broken:

No idea what to cook — People waste time trying to mentally combine random ingredients into a meal, often giving up and ordering food instead.
Food wastage — Ingredients go bad because people don’t know what recipes can be made from what’s already available in the kitchen.
Dietary restrictions go unmet — People with specific requirements (vegan, keto, gluten-free, high-protein) cannot quickly find suitable recipes for the ingredients they already have.
Recipe search doesn’t help — Traditional recipe websites require you to know what you want to cook before you search. They don’t work in reverse — starting from ingredients.
Can’t describe ingredients digitally — People standing in front of a fridge cannot easily type out every ingredient they see. A photo is the most natural way to communicate “what’s here.”
No personalization or nutrition data — Standard recipe books don’t tell you the calories, macros, or dietary tags for the specific combination of ingredients you have on hand.Problem Identification
Subtitle: The Current Problem in Home Cooking

Every day, millions of people open their fridge, stare at random ingredients, and have no idea what to cook. The existing support system for home cooks is fundamentally broken:

No idea what to cook — People waste time trying to mentally combine random ingredients into a meal, often giving up and ordering food instead.
Food wastage — Ingredients go bad because people don’t know what recipes can be made from what’s already available in the kitchen.
Dietary restrictions go unmet — People with specific requirements (vegan, keto, gluten-free, high-protein) cannot quickly find suitable recipes for the ingredients they already have.
Recipe search doesn’t help — Traditional recipe websites require you to know what you want to cook before you search. They don’t work in reverse — starting from ingredients.
Can’t describe ingredients digitally — People standing in front of a fridge cannot easily type out every ingredient they see. A photo is the most natural way to communicate “what’s here.”
No personalization or nutrition data — Standard recipe books don’t tell you the calories, macros, or dietary tags for the specific combination of ingredients you have on hand.
