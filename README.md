# meal_planner

## Specification:

### Menu Generation
1. Parse recipe files in csv or text formats to a sqlit3 database (+ sqlalchemy?)
    a. Columns include: name, ingredients (possibly a txt file name vs. individual columns in case of crazy long ingredients list), txt filename of instructions, classification (meat, veggie, side, or self-contained), allergens?
    b. Or have one database for meats/self-contained and another each for veggies and sides
2. Randomly pick (num meals) from database
    a. Weight/exclude based on: recently used, allergens, ingredient crossover (unsure about algorithm on this one, I'm pretty sure this becomes an NP problem fast and I'm not sure about what heuristics would work)
    b. If a meat gets chosen from the master database, also pick a veggie and a side to go with it, possibly with similar weighting criteria

### Shopping List Generation
1. Take generated meal list and pull all txt files of ingredients
2. Parse ingredient lists into some convenient format, incrementing quantities of repeated items rather than adding them twice
3. Save to txt or post to a service like Google tasks (https://developers.google.com/tasks/reference/rest)

### Create Safeway/Walmart Cart
1. Take generated shopping list (perhaps in txt format) and parse if needed
2. Search store pages for item names, perhaps also look for quantities and need to figure out how to tell if in stock
3. Add appropriate items to cart

### Notify Me
1. Email that contains meal names, links to instruction cards, and shopping list/ready cart to look over