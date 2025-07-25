# PaletteSnap

PaletteSnap is a fun and useful color palette collector built with CodeIgniter 4.
Upload an image, and it magically extracts the most dominant colors for you.
Great for designers, developers, and anyone who finds color inspiring.

---

## Features

- Upload images (JPG/PNG).
- Automatically extract the top 5 dominant colors.
- Store the image and its associated color palette in a database.
- Tag your palettes for easy discovery and organization.
- View all saved palettes with clear color previews.
- **Coming Soon:** Filter palettes by their assigned tags.

---

## How It Works

1.  You upload an image through the web interface.
2.  PaletteSnap uses the **ColorThief PHP** library to analyze the image.
3.  It intelligently pulls out the top 5 most dominant colors.
4.  The colors are stored in the database in HEX format (`#RRGGBB`).
5.  You can then browse, tag, and reuse your saved palettes anytime.

---

## Tech Stack

| Component         | Technology/Library          |
|:------------------|:----------------------------|
| **Framework**     | CodeIgniter 4               |
| **Language**      | PHP 8+                      |
| **Database**      | MySQL                       |
| **Color Extraction**| ColorThief PHP              |
| **Frontend**      | Bootstrap (optional), JS    |
| **Dependencies**  | Composer                    |

---

## Setup Instructions

### 1. Clone the Repo
```bash
git clone https://github.com/tarunbarkoti/pallette-snap.git
cd PaletteSnap
```

### 2. Install Dependencies & Set Up Environment
First, ensure you have PHP 8+, Composer, and MySQL installed. Then run the following commands:
```bash
composer install
cp .env.example .env
php spark key:generate
```

### 3. Configure the Database
Open the .env file you just created and update the database credentials:
```ini
database.default.hostname = localhost
database.default.database = palettesnap
database.default.username = root
database.default.password = your_password
```

Once configured, run the database migration to create the necessary tables:
```bash
php spark migrate
```

### 4. Install ColorThief Library
This might already be handled by composer install, but if not, run:
```bash
composer require ksubileau/color-thief-php
```


### 5. Run the Development Server
```bash
php spark serve
```
You can now access the application by navigating to **http://localhost:8080** in your browser.

---

## Why I Built This

I wanted to explore something creative with image processing and make a tool that’s genuinely helpful for visual creators. It’s a simple idea, but one that could grow into something powerful for designers and developers looking for quick inspiration.

---

## To-Do (Future Enhancements)

-   [ ] Implement a search feature to find palettes by tag.
-   [ ] Add user accounts for saving personal palettes.
-   [ ] Create a REST API to fetch palette data by its ID.
-   [ ] Develop a feature for suggesting palettes based on themes (e.g., "sunset," "forest").

---

## License

This project is licensed under the **MIT License**. Feel free to use it, fork it, and remix it!
