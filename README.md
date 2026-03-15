# 🥗 Family Meal Planner

A lightweight, single-page meal planner for a South Indian vegetarian family.  
Curated with love by **Suma**. Hosted via GitHub Pages — no server, no login, no fuss.

## ✨ Features

- **Today's Meals** — Pick a week & day, see all 5 meals at a glance
- **Week Plan** — Full 7-day grid view across 4 rotating weeks
- **Browse Options** — Browse all 28 options per meal type (breakfast, snack, lunch, etc.)
- **About** — Credits and version history

## 📁 File Structure

```
├── index.html   # App renderer — no food data inside
└── meals.yaml   # All meal data, credits, and changelog
```

All meal content lives in `meals.yaml`. To update meals, notes, or add a new week — only that file needs editing.

## 🍽 Meal Schedule

| Slot         | Time    |
|--------------|---------|
| Breakfast    | 7:30 am |
| Morning Snack| 10:30 am|
| Lunch        | 1:00 pm |
| Evening Snack| 4:30 pm |
| Dinner       | 7:30 pm |

## ✏️ How to Update Meals

Open `meals.yaml` and edit directly. The structure is:

```yaml
weeks:
  - week: 5
    days:
      - day: Monday
        breakfast: "Your new breakfast"
        snack10: "Fruit"
        lunch: "Your lunch"
        snack4: "Evening snack"
        dinner: "Dinner item"
```

To **inherit** lunch/dinner from another week:
```yaml
  - week: 2
    inherit_lunch_from: 1
    inherit_dinner_from: 1
```

To add a **note** to a specific meal:
```yaml
      - day: Saturday
        breakfast: "Veg Poha"
        notes:
          breakfast: "DON'T pair with Curd"
```

## 📝 Adding a Changelog Entry

In `meals.yaml`, append to the changelog under `meta`:

```yaml
meta:
  changelog:
    - version: "1.1"
      date: "2025-04-01"
      note: "Added lunch and dinner for Weeks 2, 3, 4"
```

## 🚀 Deploying to GitHub Pages

1. Create a new GitHub repository
2. Upload `index.html`, `meals.yaml`, and `README.md`
3. Go to **Settings → Pages**
4. Set source to **Deploy from a branch → main → / (root)**
5. Your app will be live at `https://<your-username>.github.io/<repo-name>`
