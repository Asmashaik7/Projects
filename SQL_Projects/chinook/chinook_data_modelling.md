/*✅ Recommended Insert Order in Chinook

Here’s the safe sequence to follow:

Order Table			Why
1	Genre			Base category, no dependencies
2	MediaType		Also independent
3	Artist			Parent for Album
4	Album			Depends on Artist
5	Track			Depends on Album, Genre, MediaType
6	Employee		Parent for Customer
7	Customer		Depends on Employee
8	Invoice			Depends on Customer
9	InvoiceLine		Depends on Invoice & Track
10	Playlist		Independent
11	PlaylistTrack	Depends on Playlist & Track

Overall Relationship Summary

Here’s the full chain in a simplified tree form:

Artist
 └── Album
      └── Track
           ├── MediaType
           ├── Genre
           ├── InvoiceLine
           │    └── Invoice
           │         └── Customer
           │              └── Employee (SupportRep)
           │
           └── PlaylistTrack
                └── Playlist

What is Data Modeling?

Data Modeling is the process of designing how data will be stored, related, and organized in your database.
There are 3 levels of it 👇
🧠 1️⃣ Conceptual Data Model (High-level plan)
Focus: What entities (tables) exist and how they’re related.
You only talk about entities (like Artist, Album, Track, Customer).
You show relationships (like Artist → Album = One-to-Many).

🟢 Example:
Artist → Album → Track
Customer → Invoice → InvoiceLine
You can draw this as a simple ER (Entity-Relationship) diagram — no SQL yet.

⚙️ 2️⃣ Logical Data Model (Structure planning)
Focus: What attributes (columns) each table will have and their data types.
Still no real database yet — just planning.
You decide:
What’s the Primary Key
What’s the Foreign Key
What are relationships (1–1, 1–many, many–many)
What columns belong to each entity

🟢 Example:
Album table → AlbumId (PK), Title, ArtistId (FK)

💾 3️⃣ Physical Data Model (Implementation in SQL)
Focus: Actually creating everything in SQL Server.
You write commands like:
CREATE TABLE
ALTER TABLE ADD CONSTRAINT
CREATE INDEX */
