<!DOCTYPE html>
<html lang="en">
<head> <meta name="google-adsense-account" content="ca-pub-6570704359501970">
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Free Recipes</title>
    <!-- Favicon -->
    <link rel="icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'><text y='90' font-size='90'>🍽️</text></svg>">
    
    <!-- Tailwind CSS via CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    
    <!-- Google Fonts - Inter & Raleway (for the title) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Raleway:wght@700;800;900&display=swap" rel="stylesheet">
    
    <style>
        body {
            font-family: 'Inter', sans-serif;
            background-color: #f8fafc; /* Light gray background */
        }
        .recipe-card {
            transition: transform 0.2s ease-in-out;
        }
        .recipe-card:hover {
            transform: translateY(-5px);
        }
        .title-gradient {
            background-image: linear-gradient(to right, #4c51bf, #6b46c1);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .modal {
            display: none;
        }
        .spinner {
            border: 4px solid rgba(0, 0, 0, 0.1);
            border-left-color: #4c51bf;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            animation: spin 1s linear infinite;
        }
        @keyframes spin {
            to { transform: rotate(360deg); }
        }
        /* Custom scrollbar for text area */
        #recipe-output::-webkit-scrollbar {
            width: 8px;
        }
        #recipe-output::-webkit-scrollbar-track {
            background: #f1f1f1;
            border-radius: 10px;
        }
        #recipe-output::-webkit-scrollbar-thumb {
            background: #888;
            border-radius: 10px;
        }
        #recipe-output::-webkit-scrollbar-thumb:hover {
            background: #555;
        }
        
        /* New styles for the colorful placeholders */
        .image-placeholder {
            width: 100%;
            height: 192px; /* h-48 equivalent */
            border-radius: 0.5rem; /* rounded-lg equivalent */
            margin-bottom: 1rem; /* mb-4 equivalent */
            display: flex;
            align-items: center;
            justify-content: center;
            color: #000;
            font-weight: bold;
            font-size: 1.5rem;
            text-align: center;
            background-size: cover;
            background-position: center;
        }
        .gradient-1 { background-image: linear-gradient(135deg, #fce38a, #f38181); }
        .gradient-2 { background-image: linear-gradient(135deg, #a8e063, #56ab2f); }
        .gradient-3 { background-image: linear-gradient(135deg, #6dd5ed, #2193b0); }
        .gradient-4 { background-image: linear-gradient(135deg, #fc00ff, #00dbde); }
        .gradient-5 { background-image: linear-gradient(135deg, #f09819, #edde5d); }
    </style>

    <!-- Google AdSense Placeholder -->
    <!--
    TO ADD GOOGLE ADSENSE, PASTE YOUR ADSENSE SCRIPT TAG HERE, BETWEEN THE <head> AND </head> TAGS.
    Example:
    <script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=YOUR_PUBLISHER_ID"
     crossorigin="anonymous"></script>
    -->
</head> <meta name="google-adsense-account" content="ca-pub-6570704359501970">
<body class="text-gray-800">

    <!-- Header -->
    <header class="bg-white shadow-md rounded-b-xl mb-8">
        <div class="container mx-auto px-4 py-6 text-center">
            <h1 class="text-5xl md:text-6xl font-extrabold text-gray-900 rounded-md">
                <span class="title-gradient font-black tracking-wide font-['Raleway']">Free Recipes</span>
            </h1>
        </div>
    </header>

    <main class="container mx-auto px-4 py-8">

        <!-- Adsense Ad Unit Placeholder -->
        <div class="my-8 text-center bg-gray-200 py-12 rounded-lg text-gray-600 font-medium">
            [AdSense Ad Placeholder: Top of Page]
        </div>

        <!-- Search Bar & Gemini Feature Button Section -->
        <div class="flex flex-col md:flex-row items-center justify-center mb-8 gap-4">
            <div class="relative w-full max-w-xl">
                <input 
                    type="text" 
                    id="search-input" 
                    placeholder="Search recipes..." 
                    class="w-full px-5 py-3 pr-12 rounded-full border border-gray-300 focus:outline-none focus:ring-2 focus:ring-purple-500 transition duration-300 shadow-md text-gray-700"
                >
                <span class="absolute right-4 top-1/2 -translate-y-1/2 text-gray-400">
                    <!-- Search SVG Icon -->
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-6 h-6">
                        <path stroke-linecap="round" stroke-linejoin="round" d="m21 21-5.197-5.197m0 0A7.5 7.5 0 1 0 5.196 5.196a7.5 7.5 0 0 0 10.607 10.607Z" />
                    </svg>
                </span>
            </div>
            <button id="open-gemini-modal" class="w-full md:w-auto px-6 py-3 bg-purple-600 text-white font-bold rounded-full shadow-md hover:bg-purple-700 transition duration-300">
                ✨ Generate a Custom Recipe ✨
            </button>
        </div>
        
        <div id="recipe-container" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
            
            <!-- Recipe Card 1: Spaghetti Bolognese -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Classic Spaghetti Bolognese</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Spaghetti Bolognese</h2>
                <p class="text-gray-600 mb-4">
                    A rich and hearty Italian classic that is perfect for a family dinner.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>500g beef mince</li>
                        <li>1 onion, chopped</li>
                        <li>2 cloves garlic, minced</li>
                        <li>1 can (400g) chopped tomatoes</li>
                        <li>150ml beef stock</li>
                        <li>Pasta to serve</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat oil in a pan and brown the mince.</li>
                        <li>Add onion and garlic, cook until soft.</li>
                        <li>Stir in chopped tomatoes and stock, bring to a simmer.</li>
                        <li>Reduce heat and let it simmer for at least 30 minutes.</li>
                        <li>Serve over cooked pasta.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 2: Avocado Toast -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Simple Avocado Toast</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Simple Avocado Toast</h2>
                <p class="text-gray-600 mb-4">
                    A quick and healthy breakfast or snack that's ready in minutes.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 ripe avocado</li>
                        <li>2 slices of your favorite bread</li>
                        <li>Pinch of salt and pepper</li>
                        <li>Optional: red pepper flakes, lemon juice</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Toast the bread to your desired crispiness.</li>
                        <li>Mash the avocado in a bowl.</li>
                        <li>Spread the mashed avocado evenly on the toast.</li>
                        <li>Sprinkle with salt, pepper, and any optional toppings.</li>
                        <li>Enjoy immediately.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 3: Chocolate Chip Cookies -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Chewy Chocolate Chip Cookies</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Chewy Chocolate Chip Cookies</h2>
                <p class="text-gray-600 mb-4">
                    The perfect sweet treat, with a soft center and slightly crisp edges.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 cup unsalted butter, softened</li>
                        <li>3/4 cup granulated sugar</li>
                        <li>3/4 cup packed brown sugar</li>
                        <li>2 large eggs</li>
                        <li>1 tsp vanilla extract</li>
                        <li>2 1/4 cups all-purpose flour</li>
                        <li>1 tsp baking soda</li>
                        <li>1/2 tsp salt</li>
                        <li>2 cups semi-sweet chocolate chips</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 375°F (190°C).</li>
                        <li>Cream butter and sugars until light and fluffy.</li>
                        <li>Beat in eggs and vanilla.</li>
                        <li>In a separate bowl, whisk flour, baking soda, and salt.</li>
                        <li>Gradually add dry ingredients to wet ingredients.</li>
                        <li>Stir in chocolate chips.</li>
                        <li>Drop spoonfuls onto a baking sheet.</li>
                        <li>Bake for 9-11 minutes, or until golden brown.</li>
                        <li>Let cool on the baking sheet for a few minutes before moving to a wire rack.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 4: Chicken Alfredo -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Creamy Chicken Alfredo</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Creamy Chicken Alfredo</h2>
                <p class="text-gray-600 mb-4">
                    A rich and savory pasta dish that's surprisingly easy to make.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 boneless, skinless chicken breasts</li>
                        <li>1 tbsp olive oil</li>
                        <li>2 cloves garlic, minced</li>
                        <li>1 1/2 cups heavy cream</li>
                        <li>1/2 cup grated Parmesan cheese</li>
                        <li>Salt and black pepper to taste</li>
                        <li>Fettuccine pasta to serve</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Cook pasta according to package directions.</li>
                        <li>Cut chicken into cubes and season with salt and pepper.</li>
                        <li>Cook chicken in olive oil until golden brown.</li>
                        <li>Add garlic and cook for 1 minute.</li>
                        <li>Pour in heavy cream, bring to a simmer.</li>
                        <li>Stir in Parmesan cheese until sauce is smooth.</li>
                        <li>Toss with cooked pasta and chicken.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 5: Caprese Salad -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Fresh Caprese Salad</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Fresh Caprese Salad</h2>
                <p class="text-gray-600 mb-4">
                    A simple and elegant salad that highlights fresh, vibrant flavors.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 ripe tomatoes, sliced</li>
                        <li>1 ball fresh mozzarella, sliced</li>
                        <li>1/2 cup fresh basil leaves</li>
                        <li>Balsamic glaze or extra virgin olive oil</li>
                        <li>Salt and black pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Arrange alternating slices of tomato, mozzarella, and basil on a platter.</li>
                        <li>Drizzle with balsamic glaze or olive oil.</li>
                        <li>Season with salt and pepper.</li>
                        <li>Serve immediately.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 6: Easy Chili -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Quick and Easy Chili</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Quick and Easy Chili</h2>
                <p class="text-gray-600 mb-4">
                    A comforting bowl of chili that's perfect for a cold evening.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb ground beef or turkey</li>
                        <li>1 can (15 oz) kidney beans, drained and rinsed</li>
                        <li>1 can (15 oz) pinto beans, drained and rinsed</li>
                        <li>1 can (15 oz) diced tomatoes</li>
                        <li>1 packet chili seasoning mix</li>
                        <li>1 cup water</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Brown the ground meat in a large pot over medium heat.</li>
                        <li>Stir in chili seasoning mix.</li>
                        <li>Add beans, diced tomatoes, and water.</li>
                        <li>Bring to a boil, then reduce heat and simmer for 20 minutes.</li>
                        <li>Serve with your favorite toppings like shredded cheese or sour cream.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 7: Lemon Garlic Roasted Chicken -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Lemon Garlic Roasted Chicken</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Lemon Garlic Roasted Chicken</h2>
                <p class="text-gray-600 mb-4">
                    A simple yet flavorful dish that's a perfect centerpiece for any meal.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 whole chicken (about 4 lbs)</li>
                        <li>1 lemon, halved</li>
                        <li>1 head garlic, separated into cloves</li>
                        <li>2 tbsp olive oil</li>
                        <li>1 tsp dried thyme</li>
                        <li>Salt and black pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 425°F (220°C).</li>
                        <li>Rub chicken with olive oil, salt, pepper, and thyme.</li>
                        <li>Place lemon halves and garlic cloves inside the chicken cavity.</li>
                        <li>Roast for 1 hour or until internal temperature reaches 165°F (74°C).</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 8: Simple Quinoa Salad -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Simple Quinoa Salad</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Simple Quinoa Salad</h2>
                <p class="text-gray-600 mb-4">
                    A light and refreshing salad that is packed with protein and nutrients.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 cup quinoa, rinsed</li>
                        <li>2 cups water or vegetable broth</li>
                        <li>1 cucumber, diced</li>
                        <li>1 bell pepper, diced</li>
                        <li>1/2 cup chopped fresh parsley</li>
                        <li>Lemon vinaigrette dressing</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Bring water or broth to a boil, add quinoa, and reduce to a simmer.</li>
                        <li>Cover and cook for 15-20 minutes, or until all liquid is absorbed.</li>
                        <li>Fluff with a fork and let cool.</li>
                        <li>Mix cooled quinoa with cucumber, bell pepper, and parsley.</li>
                        <li>Dress with lemon vinaigrette before serving.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 9: Pan-Seared Salmon -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Pan-Seared Salmon with Asparagus</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Pan-Seared Salmon with Asparagus</h2>
                <p class="text-gray-600 mb-4">
                    A quick and elegant meal that's both healthy and delicious.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 salmon fillets</li>
                        <li>1 bunch asparagus, ends trimmed</li>
                        <li>1 tbsp olive oil</li>
                        <li>1 tbsp butter</li>
                        <li>1 clove garlic, minced</li>
                        <li>Lemon wedges for serving</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Season salmon with salt and pepper.</li>
                        <li>Heat oil in a pan over medium-high heat.</li>
                        <li>Add salmon skin-side down and cook for 5-7 minutes.</li>
                        <li>Flip salmon, add butter, garlic, and asparagus.</li>
                        <li>Cook for another 5 minutes, or until salmon is cooked through and asparagus is tender-crisp.</li>
                        <li>Serve with lemon wedges.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 10: Vegetable Stir-Fry -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Vegetable Stir-Fry</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Vegetable Stir-Fry</h2>
                <p class="text-gray-600 mb-4">
                    A vibrant and customizable stir-fry that is a great way to use up veggies.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp sesame oil</li>
                        <li>1 broccoli head, chopped into florets</li>
                        <li>2 carrots, sliced</li>
                        <li>1 red bell pepper, sliced</li>
                        <li>1/2 cup snap peas</li>
                        <li>Stir-fry sauce of your choice</li>
                        <li>Cooked rice or noodles for serving</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat sesame oil in a large pan or wok over high heat.</li>
                        <li>Add vegetables and stir-fry for 5-7 minutes until tender-crisp.</li>
                        <li>Pour in stir-fry sauce and toss to coat.</li>
                        <li>Serve hot over cooked rice or noodles.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 11: Baked Mac and Cheese -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Ultimate Baked Mac and Cheese</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Ultimate Baked Mac and Cheese</h2>
                <p class="text-gray-600 mb-4">
                    A classic comfort food with a crispy, golden top and a creamy, cheesy interior.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb elbow macaroni</li>
                        <li>1/2 cup unsalted butter</li>
                        <li>1/2 cup all-purpose flour</li>
                        <li>4 cups milk</li>
                        <li>1 tsp salt</li>
                        <li>1/2 tsp black pepper</li>
                        <li>1/4 tsp paprika</li>
                        <li>3 cups shredded cheddar cheese</li>
                        <li>1 cup shredded Gruyère or Monterey Jack cheese</li>
                        <li>1 cup breadcrumbs (for topping)</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 375°F (190°C). Cook macaroni according to package directions; drain and set aside.</li>
                        <li>In a large pot, melt butter over medium heat. Whisk in flour for one minute.</li>
                        <li>Gradually whisk in milk, stirring constantly until the mixture thickens.</li>
                        <li>Remove from heat. Stir in salt, pepper, paprika, and cheeses until melted and smooth.</li>
                        <li>Add cooked macaroni to the cheese sauce and stir to combine.</li>
                        <li>Pour into a greased baking dish and top with breadcrumbs.</li>
                        <li>Bake for 20-25 minutes, or until the top is golden and bubbly.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 12: Roasted Brussels Sprouts -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Crispy Roasted Brussels Sprouts</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Crispy Roasted Brussels Sprouts</h2>
                <p class="text-gray-600 mb-4">
                    A simple and delicious side dish that makes a vegetable lover out of anyone.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb brussels sprouts, trimmed and halved</li>
                        <li>2 tbsp olive oil</li>
                        <li>1/2 tsp salt</li>
                        <li>1/4 tsp black pepper</li>
                        <li>Pinch of red pepper flakes (optional)</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 400°F (200°C).</li>
                        <li>Toss brussels sprouts with olive oil, salt, pepper, and red pepper flakes.</li>
                        <li>Spread in a single layer on a baking sheet.</li>
                        <li>Roast for 20-25 minutes, stirring halfway, until crispy and browned.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 13: Banana Bread -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Classic Banana Bread</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Banana Bread</h2>
                <p class="text-gray-600 mb-4">
                    A moist and flavorful bread that's perfect for using up overripe bananas.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 3/4 cups all-purpose flour</li>
                        <li>1 tsp baking soda</li>
                        <li>1/2 tsp salt</li>
                        <li>1/2 cup unsalted butter, softened</li>
                        <li>3/4 cup granulated sugar</li>
                        <li>2 large eggs, beaten</li>
                        <li>4 ripe bananas, mashed</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 350°F (175°C). Grease and flour a loaf pan.</li>
                        <li>In a bowl, whisk flour, baking soda, and salt.</li>
                        <li>In a separate bowl, cream butter and sugar. Beat in eggs and mashed bananas.</li>
                        <li>Add dry ingredients to the banana mixture and stir until just combined.</li>
                        <li>Pour batter into the prepared loaf pan.</li>
                        <li>Bake for 50-60 minutes, or until a toothpick inserted into the center comes out clean.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 14: Chicken Noodle Soup -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Classic Chicken Noodle Soup</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Chicken Noodle Soup</h2>
                <p class="text-gray-600 mb-4">
                    A comforting and nourishing soup that's perfect for a rainy day.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>1 lb boneless, skinless chicken breast, cubed</li>
                        <li>1 chopped onion</li>
                        <li>2 chopped carrots</li>
                        <li>2 chopped celery stalks</li>
                        <li>8 cups chicken broth</li>
                        <li>2 cups egg noodles</li>
                        <li>1/2 tsp dried thyme</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat oil in a large pot. Add chicken and cook until no longer pink.</li>
                        <li>Add onion, carrots, and celery; cook for 5 minutes until softened.</li>
                        <li>Pour in chicken broth and thyme. Bring to a boil, then reduce heat and simmer for 15 minutes.</li>
                        <li>Stir in egg noodles and cook for 8-10 minutes, or until tender.</li>
                        <li>Season with salt and pepper before serving.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 15: Homemade Pizza -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Easy Homemade Pizza</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Easy Homemade Pizza</h2>
                <p class="text-gray-600 mb-4">
                    Perfect for a fun night in, this recipe is a blank canvas for your favorite toppings.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 store-bought pizza dough</li>
                        <li>1/2 cup pizza sauce</li>
                        <li>2 cups shredded mozzarella cheese</li>
                        <li>Toppings of your choice (pepperoni, mushrooms, onions, etc.)</li>
                        <li>1 tbsp olive oil</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 450°F (230°C).</li>
                        <li>Roll out pizza dough on a floured surface to your desired thickness.</li>
                        <li>Brush the crust with olive oil.</li>
                        <li>Spread pizza sauce evenly over the dough.</li>
                        <li>Top with mozzarella cheese and your favorite toppings.</li>
                        <li>Bake for 10-15 minutes, or until the crust is golden and cheese is bubbly.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 16: Roasted Red Pepper Soup -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Creamy Roasted Red Pepper Soup</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Creamy Roasted Red Pepper Soup</h2>
                <p class="text-gray-600 mb-4">
                    A velvety and flavorful soup that is perfect for a light lunch or dinner.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>4 red bell peppers</li>
                        <li>1 tbsp olive oil</li>
                        <li>1 chopped onion</li>
                        <li>2 cloves garlic, minced</li>
                        <li>4 cups vegetable broth</li>
                        <li>1/2 cup heavy cream or coconut milk</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 400°F (200°C). Place peppers on a baking sheet and roast for 20-25 minutes, or until skin is charred.</li>
                        <li>Let peppers cool, then peel and seed them.</li>
                        <li>In a pot, heat olive oil and cook onion and garlic until soft.</li>
                        <li>Add roasted peppers and vegetable broth. Bring to a simmer.</li>
                        <li>Use an immersion blender to purée the soup until smooth.</li>
                        <li>Stir in heavy cream, season with salt and pepper, and serve.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 17: Black Bean Burgers -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Spicy Black Bean Burgers</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Spicy Black Bean Burgers</h2>
                <p class="text-gray-600 mb-4">
                    A hearty and flavorful vegetarian alternative to a classic burger.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 can (15 oz) black beans, drained and rinsed</li>
                        <li>1/2 cup breadcrumbs</li>
                        <li>1/4 cup chopped red onion</li>
                        <li>1 clove garlic, minced</li>
                        <li>1 tbsp chili powder</li>
                        <li>1 egg</li>
                        <li>Salt and pepper to taste</li>
                        <li>Burger buns and toppings for serving</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a large bowl, mash black beans with a fork, leaving some texture.</li>
                        <li>Stir in breadcrumbs, red onion, garlic, chili powder, egg, salt, and pepper.</li>
                        <li>Form into patties.</li>
                        <li>Cook patties in a lightly oiled pan over medium heat for 4-5 minutes per side, until heated through.</li>
                        <li>Serve on buns with your favorite toppings.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 18: Thai Green Curry -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Authentic Thai Green Curry</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Authentic Thai Green Curry</h2>
                <p class="text-gray-600 mb-4">
                    Aromatic, spicy, and creamy—a delicious and comforting one-pot meal.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp coconut oil</li>
                        <li>1/4 cup green curry paste</li>
                        <li>1 can (13.5 oz) full-fat coconut milk</li>
                        <li>1 lb chicken breast or firm tofu, cubed</li>
                        <li>1 chopped red bell pepper</li>
                        <li>1/2 cup bamboo shoots, sliced</li>
                        <li>1 tbsp fish sauce (or soy sauce for vegetarian)</li>
                        <li>Fresh basil leaves for garnish</li>
                        <li>Cooked jasmine rice for serving</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat coconut oil in a pot and cook green curry paste for 1 minute until fragrant.</li>
                        <li>Stir in half of the coconut milk and bring to a simmer.</li>
                        <li>Add chicken or tofu and cook until lightly browned.</li>
                        <li>Add the remaining coconut milk, red bell pepper, bamboo shoots, and fish sauce.</li>
                        <li>Simmer for 10-15 minutes, until chicken is cooked through and vegetables are tender.</li>
                        <li>Garnish with fresh basil and serve over jasmine rice.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 19: Classic Margherita Pizza -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Classic Margherita Pizza</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Margherita Pizza</h2>
                <p class="text-gray-600 mb-4">
                    A simple and fresh Italian pizza with a perfect balance of flavors.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 pizza dough ball</li>
                        <li>1/2 cup San Marzano tomato sauce</li>
                        <li>8 oz fresh mozzarella, sliced</li>
                        <li>10 fresh basil leaves</li>
                        <li>1 tbsp olive oil</li>
                        <li>Pinch of salt</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven and a pizza stone to 500°F (260°C).</li>
                        <li>Stretch or roll out the dough into a 12-inch circle.</li>
                        <li>Spread a thin layer of tomato sauce over the dough.</li>
                        <li>Arrange mozzarella slices evenly over the sauce.</li>
                        <li>Bake for 10-12 minutes, or until crust is golden and cheese is melted.</li>
                        <li>Remove from oven, top with fresh basil, drizzle with olive oil, and serve.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 20: Hearty Lentil Soup -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Hearty Lentil Soup</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Hearty Lentil Soup</h2>
                <p class="text-gray-600 mb-4">
                    A filling and nutritious vegetarian soup that's packed with flavor.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>1 chopped onion</li>
                        <li>2 chopped carrots</li>
                        <li>2 chopped celery stalks</li>
                        <li>2 cloves garlic, minced</li>
                        <li>1 cup brown or green lentils, rinsed</li>
                        <li>6 cups vegetable broth</li>
                        <li>1 can (15 oz) diced tomatoes</li>
                        <li>1 tsp cumin</li>
                        <li>1/2 tsp dried thyme</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat olive oil in a large pot. Sauté onion, carrots, and celery until softened.</li>
                        <li>Add garlic, cumin, and thyme; cook for 1 minute.</li>
                        <li>Stir in lentils, vegetable broth, and diced tomatoes.</li>
                        <li>Bring to a boil, then reduce heat and simmer for 30-40 minutes, until lentils are tender.</li>
                        <li>Season with salt and pepper to taste before serving.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 21: Classic Beef Tacos -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Classic Beef Tacos</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Beef Tacos</h2>
                <p class="text-gray-600 mb-4">
                    A fun and easy weeknight dinner that everyone can customize.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb ground beef</li>
                        <li>1 packet taco seasoning mix</li>
                        <li>1/2 cup water</li>
                        <li>8-12 taco shells or tortillas</li>
                        <li>Toppings: shredded lettuce, diced tomatoes, cheese, sour cream, salsa</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Brown ground beef in a skillet over medium-high heat. Drain excess grease.</li>
                        <li>Stir in taco seasoning and water. Bring to a simmer and cook until liquid is absorbed.</li>
                        <li>Warm taco shells or tortillas according to package directions.</li>
                        <li>Fill shells with seasoned beef and your favorite toppings.</li>
                        <li>Serve immediately.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 22: Simple Vinaigrette -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Simple Vinaigrette Dressing</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Simple Vinaigrette Dressing</h2>
                <p class="text-gray-600 mb-4">
                    An easy, homemade dressing that's far better than store-bought.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1/4 cup red wine vinegar</li>
                        <li>3/4 cup extra virgin olive oil</li>
                        <li>1 tsp Dijon mustard</li>
                        <li>1 clove garlic, minced</li>
                        <li>1 tsp honey or maple syrup</li>
                        <li>Salt and black pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a small bowl, whisk together the vinegar, mustard, and minced garlic.</li>
                        <li>Slowly drizzle in the olive oil while whisking constantly until the dressing emulsifies.</li>
                        <li>Stir in honey, salt, and pepper.</li>
                        <li>Taste and adjust seasonings as needed. Store in an airtight container.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 23: Grilled Cheese Sandwich -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Gourmet Grilled Cheese</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Gourmet Grilled Cheese</h2>
                <p class="text-gray-600 mb-4">
                    Elevate a classic comfort food with a blend of cheeses and a perfect crust.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 slices of sourdough bread</li>
                        <li>1 tbsp butter, softened</li>
                        <li>1/2 cup shredded sharp cheddar cheese</li>
                        <li>1/4 cup shredded Monterey Jack cheese</li>
                        <li>1 tsp mayonnaise (optional, for outside of bread)</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Butter one side of each slice of bread. Place one slice butter-side down in a skillet over medium heat.</li>
                        <li>Sprinkle both cheeses evenly over the bread. Top with the second slice, butter-side up.</li>
                        <li>Cook for 3-4 minutes per side, pressing gently with a spatula, until the bread is golden brown and the cheese is melted.</li>
                        <li>For an extra-crispy crust, spread a thin layer of mayonnaise on the outside of the bread before toasting.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 24: Quick Chicken Quesadillas -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Quick Chicken Quesadillas</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Quick Chicken Quesadillas</h2>
                <p class="text-gray-600 mb-4">
                    A fast, satisfying meal that's perfect for a busy day.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 cup shredded cooked chicken</li>
                        <li>1/2 cup shredded Monterey Jack cheese</li>
                        <li>2-4 flour tortillas (8-inch)</li>
                        <li>1/4 cup salsa</li>
                        <li>1 tbsp vegetable oil</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a small bowl, combine chicken, cheese, and salsa.</li>
                        <li>Heat a large skillet over medium heat and add vegetable oil.</li>
                        <li>Place one tortilla in the skillet. Spread half of the chicken mixture over half of the tortilla.</li>
                        <li>Fold the other half of the tortilla over the filling.</li>
                        <li>Cook for 2-3 minutes per side, until golden brown and the cheese is melted.</li>
                        <li>Repeat with remaining ingredients and serve with sour cream or guacamole.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 25: Classic Beef Stroganoff -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Classic Beef Stroganoff</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Beef Stroganoff</h2>
                <p class="text-gray-600 mb-4">
                    A rich and creamy dish with tender beef and mushrooms, served over noodles.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb beef sirloin, cut into strips</li>
                        <li>1 tbsp butter</li>
                        <li>1 onion, sliced</li>
                        <li>8 oz mushrooms, sliced</li>
                        <li>2 cloves garlic, minced</li>
                        <li>2 cups beef broth</li>
                        <li>1/2 cup sour cream</li>
                        <li>1 tbsp flour</li>
                        <li>Egg noodles for serving</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Cook beef in a skillet until browned; remove and set aside.</li>
                        <li>Add butter, onion, and mushrooms to the skillet; cook until tender.</li>
                        <li>Stir in garlic and flour. Gradually whisk in beef broth and bring to a simmer.</li>
                        <li>Return beef to the skillet and cook for 5-10 minutes.</li>
                        <li>Stir in sour cream until sauce is creamy. Serve over hot egg noodles.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 26: Creamy Tomato Soup -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Creamy Tomato Soup</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Creamy Tomato Soup</h2>
                <p class="text-gray-600 mb-4">
                    A smooth and comforting soup, perfect with a grilled cheese sandwich.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>1 yellow onion, chopped</li>
                        <li>2 cloves garlic, minced</li>
                        <li>1 can (28 oz) crushed tomatoes</li>
                        <li>2 cups vegetable or chicken broth</li>
                        <li>1/2 cup heavy cream</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat olive oil in a pot and sauté onion until soft. Add garlic and cook for 1 minute.</li>
                        <li>Stir in crushed tomatoes and broth. Bring to a simmer.</li>
                        <li>Use an immersion blender to puree the soup until smooth.</li>
                        <li>Stir in heavy cream and season with salt and pepper. Serve hot.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 27: Easy Pancakes -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Fluffy Buttermilk Pancakes</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Fluffy Buttermilk Pancakes</h2>
                <p class="text-gray-600 mb-4">
                    The perfect stack of fluffy, golden pancakes for a weekend breakfast.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 1/2 cups all-purpose flour</li>
                        <li>2 tbsp granulated sugar</li>
                        <li>1 1/2 tsp baking powder</li>
                        <li>1/2 tsp baking soda</li>
                        <li>1/4 tsp salt</li>
                        <li>1 1/4 cups buttermilk</li>
                        <li>1 large egg</li>
                        <li>2 tbsp melted butter</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a large bowl, whisk together dry ingredients.</li>
                        <li>In a separate bowl, whisk buttermilk, egg, and melted butter.</li>
                        <li>Pour wet ingredients into dry ingredients and mix until just combined. Do not overmix.</li>
                        <li>Heat a griddle or non-stick skillet over medium heat. Pour 1/4 cup of batter for each pancake.</li>
                        <li>Cook until bubbles form on the surface, then flip and cook for another 1-2 minutes until golden.</li>
                        <li>Serve hot with maple syrup and fresh fruit.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 28: Classic Caesar Salad -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Classic Caesar Salad</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Caesar Salad</h2>
                <p class="text-gray-600 mb-4">
                    A timeless salad with crisp romaine lettuce and a tangy, creamy dressing.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 head romaine lettuce, chopped</li>
                        <li>1 cup croutons</li>
                        <li>1/2 cup grated Parmesan cheese</li>
                        <li>For the dressing: 1/2 cup mayonnaise, 2 tbsp lemon juice, 1 tsp Dijon mustard, 1 clove garlic, minced, 1/4 tsp anchovy paste (optional), salt and pepper.</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a small bowl, whisk together all dressing ingredients until smooth.</li>
                        <li>In a large bowl, combine chopped romaine lettuce and half of the Parmesan cheese.</li>
                        <li>Pour dressing over the lettuce and toss to coat evenly.</li>
                        <li>Top with croutons and remaining Parmesan cheese before serving.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 29: Sheet Pan Sausage and Veggies -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Sheet Pan Sausage and Veggies</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Sheet Pan Sausage and Veggies</h2>
                <p class="text-gray-600 mb-4">
                    An incredibly easy and delicious one-pan meal with minimal cleanup.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>4 Italian sausages, sliced</li>
                        <li>1 red onion, cut into wedges</li>
                        <li>1 bell pepper, cut into chunks</li>
                        <li>1 zucchini, sliced</li>
                        <li>1 tbsp olive oil</li>
                        <li>1 tsp Italian seasoning</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 400°F (200°C).</li>
                        <li>Toss all ingredients together on a large baking sheet.</li>
                        <li>Spread into a single layer.</li>
                        <li>Bake for 20-25 minutes, stirring halfway, until sausage is cooked through and vegetables are tender.</li>
                        <li>Serve hot.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 30: Homemade Waffles -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Crispy Homemade Waffles</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Crispy Homemade Waffles</h2>
                <p class="text-gray-600 mb-4">
                    The perfect light and crispy waffle recipe, ideal for a lazy brunch.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 cups all-purpose flour</li>
                        <li>1 tbsp sugar</li>
                        <li>2 tsp baking powder</li>
                        <li>1/2 tsp salt</li>
                        <li>2 eggs, beaten</li>
                        <li>1 1/2 cups milk</li>
                        <li>1/2 cup vegetable oil</li>
                        <li>1 tsp vanilla extract</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a large bowl, whisk together the flour, sugar, baking powder, and salt.</li>
                        <li>In a separate bowl, combine the eggs, milk, oil, and vanilla.</li>
                        <li>Pour the wet ingredients into the dry and mix until just combined.</li>
                        <li>Pour batter into a preheated and greased waffle iron.</li>
                        <li>Cook until golden brown and crispy. Serve immediately with your favorite toppings.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 31: Shrimp Scampi -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Easy Shrimp Scampi</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Easy Shrimp Scampi</h2>
                <p class="text-gray-600 mb-4">
                    A classic Italian-American dish that's quick, elegant, and full of flavor.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb shrimp, peeled and deveined</li>
                        <li>1/2 cup butter</li>
                        <li>4 cloves garlic, minced</li>
                        <li>1/4 cup dry white wine or chicken broth</li>
                        <li>2 tbsp fresh lemon juice</li>
                        <li>1/4 cup fresh parsley, chopped</li>
                        <li>Linguine or spaghetti for serving</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Cook pasta according to package directions.</li>
                        <li>Melt butter in a large skillet over medium heat. Add garlic and cook for 1 minute.</li>
                        <li>Add shrimp and cook until pink, about 2-3 minutes.</li>
                        <li>Stir in wine and lemon juice. Bring to a simmer.</li>
                        <li>Toss with cooked pasta and fresh parsley. Serve hot.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 32: Simple Guacamole -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Simple Guacamole</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Simple Guacamole</h2>
                <p class="text-gray-600 mb-4">
                    Fresh, zesty, and perfect for dipping or as a topping.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 ripe avocados</li>
                        <li>1/4 cup finely chopped red onion</li>
                        <li>1/4 cup chopped fresh cilantro</li>
                        <li>1 jalapeño, seeded and minced (optional)</li>
                        <li>1 lime, juiced</li>
                        <li>Salt to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a medium bowl, mash the avocados with a fork.</li>
                        <li>Stir in the red onion, cilantro, jalapeño, and lime juice.</li>
                        <li>Season with salt to taste.</li>
                        <li>Serve immediately with tortilla chips.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 33: Homemade Tomato Sauce -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Classic Homemade Tomato Sauce</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Homemade Tomato Sauce</h2>
                <p class="text-gray-600 mb-4">
                    A rich and flavorful sauce that's perfect for pasta or pizza.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>1 yellow onion, finely chopped</li>
                        <li>3 cloves garlic, minced</li>
                        <li>1 can (28 oz) crushed tomatoes</li>
                        <li>1/2 cup water</li>
                        <li>1 tsp dried oregano</li>
                        <li>1 tsp dried basil</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat olive oil in a large pot. Sauté onion until soft.</li>
                        <li>Add garlic and cook for 1 minute.</li>
                        <li>Stir in crushed tomatoes, water, oregano, and basil.</li>
                        <li>Bring to a simmer, then reduce heat and cook for 20-30 minutes, stirring occasionally.</li>
                        <li>Season with salt and pepper.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 34: One-Pot Lemon Herb Pasta -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">One-Pot Lemon Herb Pasta</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">One-Pot Lemon Herb Pasta</h2>
                <p class="text-gray-600 mb-4">
                    An incredibly simple and flavorful pasta dish with minimal cleanup.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>12 oz spaghetti or fettuccine</li>
                        <li>4 cups vegetable broth</li>
                        <li>1 cup cherry tomatoes, halved</li>
                        <li>2 tbsp butter</li>
                        <li>1/2 cup fresh basil leaves</li>
                        <li>Juice and zest of 1 lemon</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a large pot, combine pasta, broth, and cherry tomatoes.</li>
                        <li>Bring to a boil over high heat, then reduce to a simmer.</li>
                        <li>Cook for 8-10 minutes, stirring frequently, until pasta is al dente and most of the liquid has been absorbed.</li>
                        <li>Remove from heat. Stir in butter, lemon juice, lemon zest, and fresh basil.</li>
                        <li>Season with salt and pepper and serve immediately.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 35: Easy Black Bean Soup -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Easy Black Bean Soup</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Easy Black Bean Soup</h2>
                <p class="text-gray-600 mb-4">
                    A simple and hearty soup that's quick to make and full of flavor.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>1 onion, chopped</li>
                        <li>1 bell pepper, chopped</li>
                        <li>2 cloves garlic, minced</li>
                        <li>2 cans (15 oz) black beans, drained and rinsed</li>
                        <li>4 cups vegetable broth</li>
                        <li>1 tsp cumin</li>
                        <li>1/2 tsp chili powder</li>
                        <li>Optional toppings: sour cream, cilantro, lime wedges</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat olive oil in a large pot. Sauté onion and bell pepper until soft.</li>
                        <li>Add garlic, cumin, and chili powder; cook for 1 minute.</li>
                        <li>Stir in black beans and vegetable broth. Bring to a boil.</li>
                        <li>Reduce heat and simmer for 15 minutes. Use an immersion blender to puree a portion of the soup for a creamier texture.</li>
                        <li>Serve hot with your favorite toppings.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 36: Crispy Baked Chicken Wings -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Crispy Baked Chicken Wings</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Crispy Baked Chicken Wings</h2>
                <p class="text-gray-600 mb-4">
                    Get perfectly crispy wings without the mess of deep-frying.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 lbs chicken wings, patted dry</li>
                        <li>1 tsp baking powder (aluminum-free)</li>
                        <li>1/2 tsp salt</li>
                        <li>1/4 tsp black pepper</li>
                        <li>Sauce of your choice (e.g., BBQ, buffalo)</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 425°F (220°C). Line a baking sheet with foil and place a wire rack on top.</li>
                        <li>In a large bowl, toss wings with baking powder, salt, and pepper until evenly coated.</li>
                        <li>Arrange wings in a single layer on the wire rack.</li>
                        <li>Bake for 40-50 minutes, flipping halfway, until skin is golden and crispy.</li>
                        <li>Toss wings with your favorite sauce and serve.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 37: Simple Fried Rice -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Quick & Simple Fried Rice</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Quick & Simple Fried Rice</h2>
                <p class="text-gray-600 mb-4">
                    A delicious way to use up leftover rice and any vegetables you have on hand.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 cups cooked, chilled rice</li>
                        <li>1 tbsp vegetable oil</li>
                        <li>1/2 cup chopped onion</li>
                        <li>1/2 cup frozen peas and carrots</li>
                        <li>1 egg, lightly beaten</li>
                        <li>2 tbsp soy sauce</li>
                        <li>1 tsp sesame oil</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat vegetable oil in a large skillet or wok over high heat.</li>
                        <li>Add onion and cook for 1 minute. Add peas and carrots and cook for 2-3 minutes.</li>
                        <li>Push vegetables to one side of the pan. Pour the beaten egg into the other side and scramble it.</li>
                        <li>Add the chilled rice to the pan and break it up with a spatula.</li>
                        <li>Stir everything together, then pour soy sauce and sesame oil over the rice. Stir to combine.</li>
                        <li>Cook for another 2-3 minutes until heated through.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 38: Homemade Hummus -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Creamy Homemade Hummus</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Creamy Homemade Hummus</h2>
                <p class="text-gray-600 mb-4">
                    Skip the store-bought version and make this smooth, velvety dip at home.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 can (15 oz) chickpeas, rinsed and drained</li>
                        <li>1/4 cup tahini</li>
                        <li>1/4 cup lemon juice</li>
                        <li>1 clove garlic</li>
                        <li>2 tbsp olive oil</li>
                        <li>1/2 tsp salt</li>
                        <li>2-4 tbsp cold water</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a food processor, combine chickpeas, tahini, lemon juice, garlic, olive oil, and salt.</li>
                        <li>Blend until smooth, scraping down the sides as needed.</li>
                        <li>With the motor running, slowly add cold water, one tablespoon at a time, until the hummus reaches your desired creamy consistency.</li>
                        <li>Transfer to a bowl, drizzle with a little olive oil, and serve with pita bread or vegetables.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 39: Classic Lasagna -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Hearty Classic Lasagna</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Hearty Classic Lasagna</h2>
                <p class="text-gray-600 mb-4">
                    A family-favorite that's layered with rich meat sauce, creamy cheese, and tender pasta.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb ground beef</li>
                        <li>1 onion, chopped</li>
                        <li>2 cloves garlic, minced</li>
                        <li>1 jar (24 oz) marinara sauce</li>
                        <li>1 container (15 oz) ricotta cheese</li>
                        <li>1 large egg</li>
                        <li>1/4 cup grated Parmesan cheese</li>
                        <li>12 lasagna noodles, cooked</li>
                        <li>2 cups shredded mozzarella cheese</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 375°F (190°C).</li>
                        <li>Brown ground beef in a skillet. Drain grease. Add onion and garlic; cook until soft. Stir in marinara sauce.</li>
                        <li>In a separate bowl, mix ricotta, egg, and Parmesan.</li>
                        <li>Spread a thin layer of meat sauce on the bottom of a 9x13-inch baking dish. Top with 3 noodles, a third of the ricotta mixture, and a third of the mozzarella. Repeat layers.</li>
                        <li>Bake for 30 minutes, or until bubbly and golden.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 40: Blueberry Muffins -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Tender Blueberry Muffins</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Tender Blueberry Muffins</h2>
                <p class="text-gray-600 mb-4">
                    Soft, light, and bursting with juicy blueberries—a perfect morning treat.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 1/2 cups all-purpose flour</li>
                        <li>1/2 cup granulated sugar</li>
                        <li>2 tsp baking powder</li>
                        <li>1/2 tsp salt</li>
                        <li>1 large egg</li>
                        <li>1/2 cup milk</li>
                        <li>1/4 cup vegetable oil</li>
                        <li>1 cup fresh or frozen blueberries</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 400°F (200°C). Line a muffin tin with paper liners.</li>
                        <li>In a large bowl, whisk together flour, sugar, baking powder, and salt.</li>
                        <li>In a separate bowl, whisk egg, milk, and oil. Pour into the dry ingredients and stir until just combined.</li>
                        <li>Gently fold in the blueberries.</li>
                        <li>Fill muffin cups about two-thirds full. Bake for 18-20 minutes.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 41: Garlic Bread -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Easy Homemade Garlic Bread</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Easy Homemade Garlic Bread</h2>
                <p class="text-gray-600 mb-4">
                    Crispy on the outside, soft on the inside, and full of garlicky goodness.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 loaf of French bread or baguette</li>
                        <li>1/2 cup softened butter</li>
                        <li>3 cloves garlic, minced</li>
                        <li>1 tbsp fresh parsley, chopped</li>
                        <li>1/4 tsp salt</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 350°F (175°C).</li>
                        <li>Slice the bread lengthwise.</li>
                        <li>In a small bowl, mix together butter, minced garlic, parsley, and salt.</li>
                        <li>Spread the mixture evenly on the cut sides of the bread.</li>
                        <li>Bake for 10-15 minutes, or until the edges are golden and crispy.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 42: Classic Shepherd's Pie -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Classic Shepherd's Pie</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Shepherd's Pie</h2>
                <p class="text-gray-600 mb-4">
                    A comforting and savory pie with a delicious meat and vegetable filling topped with mashed potatoes.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb ground beef or lamb</li>
                        <li>1 chopped onion</li>
                        <li>1 cup mixed vegetables (peas, carrots, corn)</li>
                        <li>2 cups beef broth</li>
                        <li>1 tbsp flour</li>
                        <li>3 cups mashed potatoes</li>
                        <li>1/2 cup shredded cheddar cheese</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 375°F (190°C).</li>
                        <li>Brown meat in a large skillet. Drain fat. Add onion and cook until soft.</li>
                        <li>Stir in vegetables and flour. Cook for 1 minute. Add broth and simmer until thickened.</li>
                        <li>Transfer meat mixture to a baking dish. Top with mashed potatoes, spreading evenly. Sprinkle with cheese.</li>
                        <li>Bake for 20-25 minutes, or until golden and bubbly.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 43: Chicken and Veggie Skewers -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Chicken and Veggie Skewers</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Chicken and Veggie Skewers</h2>
                <p class="text-gray-600 mb-4">
                    Perfect for grilling, these skewers are colorful, healthy, and delicious.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 lb chicken breast, cut into 1-inch cubes</li>
                        <li>1 red bell pepper, cut into chunks</li>
                        <li>1 zucchini, sliced thick</li>
                        <li>1 red onion, cut into chunks</li>
                        <li>1/4 cup olive oil</li>
                        <li>2 tbsp lemon juice</li>
                        <li>1 tsp dried oregano</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a large bowl, whisk together olive oil, lemon juice, oregano, salt, and pepper.</li>
                        <li>Add chicken and vegetables and toss to coat evenly.</li>
                        <li>Thread chicken and vegetables onto skewers.</li>
                        <li>Preheat grill to medium-high heat.</li>
                        <li>Grill skewers for 10-15 minutes, turning occasionally, until chicken is cooked through.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 44: Simple Roasted Potatoes -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Simple Roasted Potatoes</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Simple Roasted Potatoes</h2>
                <p class="text-gray-600 mb-4">
                    Crispy on the outside and fluffy on the inside, a perfect side dish.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>2 lbs potatoes, cubed</li>
                        <li>2 tbsp olive oil</li>
                        <li>1 tsp salt</li>
                        <li>1/2 tsp black pepper</li>
                        <li>1 tsp paprika</li>
                        <li>1/2 tsp garlic powder</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 425°F (220°C).</li>
                        <li>In a large bowl, toss potatoes with olive oil and seasonings.</li>
                        <li>Spread in a single layer on a baking sheet.</li>
                        <li>Roast for 30-40 minutes, flipping halfway, until golden brown and crispy.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 45: Lemon Bars -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Zesty Lemon Bars</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Zesty Lemon Bars</h2>
                <p class="text-gray-600 mb-4">
                    A tangy and sweet dessert with a buttery shortbread crust.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>For the crust: 1 cup all-purpose flour, 1/2 cup unsalted butter (cold, cubed), 1/4 cup powdered sugar, 1/4 tsp salt.</li>
                        <li>For the filling: 2 large eggs, 3/4 cup granulated sugar, 1/4 cup lemon juice, 1 tbsp lemon zest.</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 350°F (175°C). Line an 8x8-inch pan with parchment paper.</li>
                        <li>For the crust, combine flour, butter, powdered sugar, and salt in a food processor or with your hands until crumbly. Press into the prepared pan.</li>
                        <li>Bake crust for 15-20 minutes until lightly golden.</li>
                        <li>For the filling, whisk together eggs, sugar, lemon juice, and zest. Pour over the hot crust.</li>
                        <li>Bake for 20-25 minutes until the filling is set. Let cool completely before slicing and serving.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 46: Simple Marinara Sauce -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-1">Simple Marinara Sauce</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Simple Marinara Sauce</h2>
                <p class="text-gray-600 mb-4">
                    A versatile and fresh sauce that forms the base of many Italian dishes.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 tbsp olive oil</li>
                        <li>4 cloves garlic, minced</li>
                        <li>1 can (28 oz) crushed tomatoes</li>
                        <li>1 tsp dried basil</li>
                        <li>1/2 tsp dried oregano</li>
                        <li>Pinch of red pepper flakes (optional)</li>
                        <li>Salt and black pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat olive oil in a saucepan over medium heat. Sauté minced garlic for 1 minute until fragrant.</li>
                        <li>Add crushed tomatoes, basil, oregano, and red pepper flakes. Stir to combine.</li>
                        <li>Bring to a simmer, then reduce heat and let the sauce cook for at least 15 minutes to allow flavors to meld.</li>
                        <li>Season with salt and pepper.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 47: Tuna Melts -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-2">Quick Tuna Melts</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Quick Tuna Melts</h2>
                <p class="text-gray-600 mb-4">
                    A comforting and classic sandwich that's perfect for a quick lunch.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 can (5 oz) tuna, drained</li>
                        <li>2 tbsp mayonnaise</li>
                        <li>1 stalk celery, finely chopped</li>
                        <li>1/4 tsp black pepper</li>
                        <li>4 slices of bread</li>
                        <li>4 slices of cheddar or Swiss cheese</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a bowl, mix drained tuna, mayonnaise, celery, and pepper.</li>
                        <li>Assemble sandwiches by placing two slices of cheese and the tuna mixture between two slices of bread.</li>
                        <li>Melt butter or spray a non-stick skillet over medium heat.</li>
                        <li>Grill the sandwiches for 3-4 minutes per side, or until golden brown and the cheese is melted.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 48: Chocolate Brownies -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-3">Fudgy Chocolate Brownies</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Fudgy Chocolate Brownies</h2>
                <p class="text-gray-600 mb-4">
                    Rich, decadent, and incredibly fudgy brownies—a chocolate lover's dream.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1/2 cup unsalted butter</li>
                        <li>1 cup granulated sugar</li>
                        <li>2 large eggs</li>
                        <li>1 tsp vanilla extract</li>
                        <li>1/2 cup all-purpose flour</li>
                        <li>1/3 cup unsweetened cocoa powder</li>
                        <li>1/4 tsp baking powder</li>
                        <li>1/4 tsp salt</li>
                        <li>1/2 cup chocolate chips (optional)</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Preheat oven to 350°F (175°C). Grease and flour an 8x8-inch baking pan.</li>
                        <li>In a saucepan, melt butter and stir in sugar. Remove from heat.</li>
                        <li>Stir in eggs and vanilla. In a separate bowl, whisk flour, cocoa powder, baking powder, and salt.</li>
                        <li>Add dry ingredients to wet ingredients and stir until just combined. Fold in chocolate chips.</li>
                        <li>Pour batter into prepared pan. Bake for 20-25 minutes. Do not overbake.</li>
                    </ol>
                </div>
            </div>

            <!-- Recipe Card 49: Classic Hummus with Pita -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-4">Classic Hummus with Pita</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Classic Hummus with Pita</h2>
                <p class="text-gray-600 mb-4">
                    A simple and savory dip that is perfect for a light lunch or snack.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1 can (15 oz) chickpeas, rinsed and drained</li>
                        <li>1/4 cup tahini</li>
                        <li>1/4 cup fresh lemon juice</li>
                        <li>2 tbsp olive oil</li>
                        <li>1 clove garlic, minced</li>
                        <li>Salt to taste</li>
                        <li>Pita bread or fresh vegetables for dipping</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>In a food processor, combine chickpeas, tahini, lemon juice, olive oil, garlic, and salt.</li>
                        <li>Blend until very smooth, scraping down the sides as needed.</li>
                        <li>Serve in a bowl with a drizzle of olive oil and a sprinkle of paprika.</li>
                    </ol>
                </div>
            </div>
            
            <!-- Recipe Card 50: Hearty Beef Stew -->
            <div class="bg-white rounded-xl shadow-md p-6 recipe-card">
                <div class="image-placeholder gradient-5">Hearty Beef Stew</div>
                <h2 class="text-2xl font-bold text-gray-900 mb-2">Hearty Beef Stew</h2>
                <p class="text-gray-600 mb-4">
                    A comforting and savory stew with tender beef and chunky vegetables, perfect for a cold evening.
                </p>
                <div class="mb-4">
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Ingredients</h3>
                    <ul class="list-disc list-inside text-gray-600">
                        <li>1.5 lbs beef stew meat, cut into 1-inch cubes</li>
                        <li>2 tbsp vegetable oil</li>
                        <li>1 large onion, chopped</li>
                        <li>2 cloves garlic, minced</li>
                        <li>2 cups beef broth</li>
                        <li>1 cup red wine (optional)</li>
                        <li>2 potatoes, peeled and cubed</li>
                        <li>2 carrots, sliced thick</li>
                        <li>1 tsp dried thyme</li>
                        <li>Salt and pepper to taste</li>
                    </ul>
                </div>
                <div>
                    <h3 class="text-lg font-semibold text-gray-800 mb-1">Instructions</h3>
                    <ol class="list-decimal list-inside text-gray-600">
                        <li>Heat oil in a large pot or Dutch oven over medium-high heat. Brown the beef on all sides.</li>
                        <li>Add onion and cook until softened. Add garlic and cook for
