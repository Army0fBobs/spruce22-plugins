# Grocery Layout

How FunnyPenny organizes your grocery list. Edit this to match the store
you actually shop at — the section order should be the order you walk it.

## Section order

<!-- The sections of YOUR grocery store, in walking order. Default is a
typical US supermarket; rename or reorder to match yours. Add/remove rows
as needed. Anything not categorized lands in "Other" at the end. -->

1. Produce
2. Bakery
3. Deli
4. Meat & Seafood
5. Dairy
6. Frozen
7. Pantry / Dry Goods
8. Condiments & Sauces
9. Snacks
10. Beverages
11. Household / Paper
12. Other

## Pantry staples (assume on hand)

<!-- Things you basically always have. FunnyPenny will skip these when
generating the grocery list, unless you say "include staples" or note
that you're out. Add or remove freely. -->

- Olive oil
- Butter
- Salt, pepper
- Garlic
- Onions (yellow)
- Eggs
- All-purpose flour
- Sugar
- Rice
- Pasta
- Soy sauce
- Vinegar (white, balsamic)

## Ingredient overrides

<!-- When FunnyPenny would categorize something into the "wrong" section
for your store, override it here. Format: `<ingredient> -> <section name>`.
Examples below — replace with your own store's quirks. -->

- Tortillas -> Bakery
- Tofu -> Produce
- Bacon -> Meat & Seafood
- Smoked salmon -> Deli

## Quantity notes

<!-- Personal conventions for quantities. Edit freely. -->

- Default to standard US units unless you note otherwise.
- "A bunch" of herbs = 1 bunch (don't try to convert).
- Milk: assume gallons unless you say otherwise.
