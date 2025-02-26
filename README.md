# Restaurant Recommender System with Prolog and Python

## Overview

This project implements a **Restaurant Recommender System** using **Prolog** for knowledge-based reasoning and **Python (pyswip)** to interact with Prolog. The system allows users to specify preferences such as price range, dietary needs, cuisine type, seating options, and payment methods to receive restaurant recommendations.

## Features

- ✅ **Uses Prolog for logical inference and reasoning**
- ✅ **Python integration with `pyswip` to interact with Prolog**
- ✅ **Dynamic knowledge base of restaurants with customizable attributes**
- ✅ **User-friendly interface for selecting preferences**
- ✅ **Multivalue attributes like dietary needs, price range, and ratings**
- ✅ **Interactive recommendation system based on user input**

## Installation

Ensure you have **SWI-Prolog** and **pyswip** installed:

```bash
# Install SWI-Prolog
apt-get install -q swi-prolog

# Install pyswip for Python-Prolog interaction
pip install -q pyswip
```

## How to Use

Run the script:

```bash
python restaurant_recommender.py
```

The system will ask for user preferences such as price, dietary restrictions, and seating type, then recommend the best matching restaurant.

## Code Structure

| File | Description |
|------|------------|
| `restaurant_recommender.py` | Python script that interacts with Prolog for restaurant recommendations |
| `restaurant_kb.pl` | Prolog knowledge base containing restaurant facts and rules |

## Knowledge Base (Prolog)

The **Prolog knowledge base** (`restaurant_kb.pl`) defines restaurant rules based on attributes like:
- **Operating hours**: `breakfast, lunch, dinner, late night`
- **Price range**: `<10, <20, <30, <50`
- **Dietary needs**: `vegan, vegetarian, gluten free, meat`
- **Ratings**: `5 stars, 4 stars, 3 stars`
- **Walking distance**: `<5, <10, <20, <30`
- **Cuisine type**: `indian, american, asian, greek, british, international, etc.`
- **Seating type**: `indoor, outdoor, none`
- **Payment options**: `apple pay, card, cash`
- **WiFi availability**: `yes/no`

Example Prolog rule:

```prolog
restaurant('Chicken Shop') :- 
    (hours('lunch'); hours('dinner'); hours('late night')), 
    price('<10'), 
    (diet_needs('vegan'); diet_needs('meat')), 
    rating('5 stars'), 
    walking_distance('<20'), 
    cuisine_type('american'), 
    seating_type('indoor'), 
    (payment_options('apple pay'); payment_options('card'); payment_options('cash')), 
    wifi(yes).
```

## Python-Prolog Interaction

- The Python script **sets up the Prolog interpreter** using `pyswip`.
- Uses `menuask` and `ask` to collect user preferences interactively.
- Calls `restaurant(X)` in Prolog to retrieve the best matching restaurant.

### Running the Recommendation System

```bash
Welcome to the restaurant recommender.

Please choose your preference for hours. 
Enter the number: 
1. breakfast
2. lunch
3. dinner
4. late night

Your input: 2

Please choose your price range:
1. <10
2. <20
3. <30
4. <50

Your input: 2

We recommend:
DODAM KOREA
```

