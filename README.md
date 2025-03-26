# Dishcovery - Recipe Finder App 🍝

## Overview

Dishcovery is a web application that helps users discover recipes based on available ingredients. Users can search for recipes by entering an ingredient, view detailed step-by-step cooking instructions, and save favorite recipes for future reference.

## Deployment link for Main branch

## Features

- **Home Page:** Search for recipes by ingredient, view search results in a grid.
- **Recipe Page:** View detailed recipe information, including ingredients, instructions, and a video tutorial (if available).
- **Favorites Page:** Save and manage favorite recipes using local storage.

## Technologies Used

- **Frontend:** HTML, CSS, Bootstrap, Vanilla JavaScript
- **API:** [TheMealDB API](https://www.themealdb.com/api.php)
- **Storage:** LocalStorage for saving favorite recipes
- **Build Tool:** [Vite](https://vitejs.dev/) for fast and optimized development

## Running the Project

Dishcovery is built using Vite as a Vanilla JavaScript project. To run the project locally, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/your-repo/dishcovery.git
   cd dishcovery
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Start the development server:
   ```sh
   npm run dev
   ```
4. Open the project in your browser at `http://localhost:5173/`.

## Branching Strategy & Code Review Process

We follow a feature-branch workflow to ensure a clean and structured development process.

### Creating a Branch

1. Fetch the latest changes and create a new branch:
   ```sh
   git checkout main
   git pull origin main
   git checkout -b task/ticket_4-create-recipe-card
   ```

### Committing & Pushing Code

2. Add changes and commit with a meaningful message:
   ```sh
   git add .
   git commit -m "Implemented recipe card component"
   ```
3. Push changes to the remote branch:
   ```sh
   git push origin task/ticket_4-create-recipe-card
   ```

### Code Review & Merging

4. Create a pull request (PR) on GitHub:

   - Ensure your branch is up to date with `main`.
   - Request at least one team member to review the code.
   - The code author cannot merge their own PR; approval is required.

5. Once approved, merge the PR into `main`.

6. Delete the feature branch after merging:
   ```sh
   git branch -d task/ticket_4-create-recipe-card
   git push origin --delete task/ticket_4-create-recipe-card
   ```

## API Endpoints & Example Responses

### Search for Recipes by Ingredient

```
GET https://www.themealdb.com/api/json/v1/1/filter.php?i=SEARCH_TERM
```

- ``: User input (spaces replaced with `\_`)
- **Response Example:**

```json
{
  "meals": [
    {
      "strMeal": "Chicken Alfredo Pasta",
      "strMealThumb": "https://www.themealdb.com/images/media/meals/xxxyyy.jpg",
      "idMeal": "52772"
    },
    {
      "strMeal": "Garlic Butter Chicken",
      "strMealThumb": "https://www.themealdb.com/images/media/meals/aaabbb.jpg",
      "idMeal": "52831"
    }
  ]
}
```

### Get Recipe Details

```
GET https://www.themealdb.com/api/json/v1/1/lookup.php?i=RECIPE_ID
```

- ``: Unique ID of a recipe
- **Response Example:**

```json
{
  "meals": [
    {
      "idMeal": "52772",
      "strMeal": "Chicken Alfredo Pasta",
      "strCategory": "Italian",
      "strArea": "Italian",
      "strInstructions": "Cook the pasta, prepare the sauce...",
      "strMealThumb": "https://www.themealdb.com/images/media/meals/xxxyyy.jpg",
      "strIngredient1": "Chicken",
      "strIngredient2": "Pasta",
      "strIngredient3": "Cream",
      "strMeasure1": "200g",
      "strMeasure2": "250g",
      "strMeasure3": "100ml",
      "strYoutube": "https://www.youtube.com/watch?v=example"
    }
  ]
}
```

## Page Descriptions

### Home Page

- **Navigation Bar:** Reusable navbar with links to Home and Favorites.
- **Hero Section:** Eye-catching banner with a call-to-action.
- **Search Bar:** Users can input an ingredient and search for recipes.
- **Recipe Grid:** Displays search results in a card format with a title, image, and action buttons.

### Recipe Page

- **Title, Category, and Country:** Displayed at the top.
- **Ingredients List:** Ingredients and measurements shown in a structured format.
- **Instructions:** Step-by-step guide for preparing the dish.
- **YouTube Link:** If available, a button to watch the recipe tutorial.

### Favorites Page

- **Stored Recipes:** Displays saved recipes from LocalStorage.
- **Remove Button:** Allows users to delete recipes from favorites.

## Development Tickets

### 1. Implement Navigation Bar

- Create a reusable navbar with Home and Favorites links.
- Ensure proper routing and UI consistency across pages.

### 2. Design Hero Section

- Add a prominent heading and subheading.
- Display an engaging image next to the text.

### 3. Implement Search Bar & API Call

- Create an input field for users to enter an ingredient.
- Fetch data from TheMealDB API based on user input.
- Display results dynamically.

### 4. Create Recipe Card HTML Structure

- Design a static card template using Bootstrap.
- Include image, title, and buttons for interaction.

### 5. Display Recipe Cards Dynamically

- Loop through API response and generate cards.
- Append cards to the recipe grid dynamically.

### 6. Navigate to Recipe Page & Fetch Recipe Data

- Clicking "View Recipe" should redirect with `idMeal` as a query parameter.
- Fetch and display recipe details based on the `idMeal`.

### 7. Design Recipe Page Layout

- Display recipe title, category, country, and details.
- Show ingredients, instructions, and YouTube link if available.

### 8. Implement Favorites Functionality

- Clicking "Add to Favorites" saves the recipe in LocalStorage.
- Display saved recipes on the Favorites page.

### 9. Style Favorites Page

- Ensure consistent styling with the Home Page.
- Allow users to remove recipes from favorites.

This README provides a structured plan for developing Dishcovery with clear goals, tasks, and example API responses. 🚀
