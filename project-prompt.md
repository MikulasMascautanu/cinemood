# 🎬 Personal Movie Catalog (ČSFD)

A web application for managing and browsing my personal list of movies bookmarked on [ČSFD.cz](https://www.csfd.cz/).  
The app will scrape/fetch movie data from ČSFD and store it in a database, making it easy to filter, search, and visualize movies by genre, year, rating, and other attributes.

---

## ✅ Goals

- Import my existing ČSFD bookmarks (hundreds of links).
- Fetch movie details (title, year, genre, country, rating, poster, etc.) from ČSFD.
- Store data in a proper **database** (SQLite with Prisma ORM).
- Provide a **web frontend** to:
  - Browse movies (grid view with posters).
  - Filter by year, genre, country, rating.
  - Search by title.
  - View detailed movie information.
- Allow updates:
  - Automatically fetch data when a new movie is added.
  - On-demand "Refresh" button to re-fetch movie details.
- Use **TailwindCSS** for UI styling.
- Version control with **GitHub**.

---

## 📦 Tech Stack

- **Language**: TypeScript
- **Frontend**: React (Vite) + TailwindCSS
- **Backend**: Node.js + Express
- **Database**: SQLite + Prisma
- **Scraping**: `axios` + `cheerio`
- **Hosting**:
  - Frontend → Netlify / Vercel
  - Backend → Railway / Render
- **Versioning**: GitHub

---

## 🗂 Database Schema (draft)

```ts
interface Movie {
	id: string; // Unique identifier (CSFD link slug or hash)
	title: string;
	year: number;
	genres: string[];
	country: string;
	rating: number; // CSFD rating (%)
	posterUrl?: string;
	link: string; // Original CSFD link
	fetchedAt: Date; // Last time data was fetched
}
```
