# Chinook Music Store Analysis

## Project Summary

In this project, I used SQL to analyse the Chinook music store database and answer questions about artists, albums, music genres, and track sales. I wanted to understand which genres generate the most revenue and what factors might explain the differences in their sales performance.

## Business Questions

1. Which artists have recorded at least one album?
2. Which artists have no recorded album?
3. Which artists have recorded more than one album?
4. Which genres generate the most revenue?
5. Which genres sell in the highest quantities?
6. Which genres generate the highest total sales value?
7. Which tracks generate the most revenue within the four top-performing genres?
8. Which tracks generate the most revenue within the other genres?
9. How many tracks are available in the four top-performing genres?
10. How many tracks are available in the other genres?

## Dataset

**Chinook Database**

[Chinook Database](https://github.com/lerocha/chinook-database
)

The Chinook database contains information about a digital music store, including artists, albums, tracks, genres, customers, and sales records.

## Tools Used

- PostgreSQL

## Key Findings and Insights

- **Revenue concentration:** Rock, Latin, Metal, and Alternative & Punk account for 73.50% of total sales value. Rock contributes the largest share at 35.50%, followed by Latin at 16.41%.

- **Quantity sold:** The four leading genres account for 77.19% of the total quantity sold and 73.50% of total sales value. This helps explain why they are the top revenue-generating genres.

- **Track revenue comparison:** Some tracks within the other genres recorded higher individual revenue than tracks within the four leading genres. Despite this, the four leading genres generated more total revenue, which led me to investigate the number of tracks available across the genres.

- **Track catalogue:** The four leading genres contain 2,582 tracks, while the other genres contain 921 tracks. This shows that the leading genres make up a larger share of the store's music catalogue, which may help explain their strong revenue contribution.

- **Catalogue size and sales performance:** The four leading genres account for 73.70% of available tracks and 73.50% of total sales value. Their share of the total quantity sold is even higher, at 77.19%, indicating that their tracks sell in higher quantities per available track than those in the other genres.

## Query Explanations and Results

### 1. Artists Who Have Recorded at Least One Album
```sql
SELECT DISTINCT
      ar.name AS artist_name
FROM artist ar
INNER JOIN album ab
   ON ar.artist_id=ab.artist_id;
```
| artist_name                                                                           |
|---------------------------------------------------------------------------------------|
| O Rappa                                                                               |
| R.E.M.                                                                                |
| Miles Davis                                                                           |
| Lenny Kravitz                                                                         |
| Os Paralamas Do Sucesso                                                               |
| Mônica Marianno                                                                       |
| Marisa Monte                                                                          |
| Chico Science & Nação Zumbi                                                           |
| Itzhak Perlman                                                                        |
| Cássia Eller                                                                          |
| Smashing Pumpkins                                                                     |
| JET                                                                                   |
| The Posies                                                                            |
| Dread Zeppelin                                                                        |
| Frank Sinatra                                                                         |
| Orchestre Révolutionnaire et Romantique & John Eliot Gardiner                         |
| Soundgarden                                                                           |
| Gonzaguinha                                                                           |
| Cidade Negra                                                                          |
| Marvin Gaye                                                                           |
| Nicolaus Esterhazy Sinfonia                                                           |
| Eugene Ormandy                                                                        |
| The Office                                                                            |
| Pink Floyd                                                                            |
| The King's Singers                                                                    |
| Van Halen                                                                             |
| Michele Campanella                                                                    |
| Gerald Moore                                                                          |
| Bruce Dickinson                                                                       |
| Academy of St. Martin in the Fields Chamber Ensemble & Sir Neville Marriner           |
| Kent Nagano and Orchestre de l'Opéra de Lyon                                          |
| Milton Nascimento                                                                     |
| Amy Winehouse                                                                         |
| R.E.M. Feat. Kate Pearson                                                             |
| Elis Regina                                                                           |
| Queen                                                                                 |
| Lulu Santos                                                                           |
| Les Arts Florissants & William Christie                                               |
| Aquaman                                                                               |
| Luciana Souza/Romero Lubambo                                                          |
| Battlestar Galactica (Classic)                                                        |
| Rush                                                                                  |
| Godsmack                                                                              |
| Guns N' Roses                                                                         |
| Skank                                                                                 |
| Emerson String Quartet                                                                |
| BackBeat                                                                              |
| Royal Philharmonic Orchestra & Sir Thomas Beecham                                     |
| Academy of St. Martin in the Fields, John Birch, Sir Neville Marriner & Sylvia McNair |
| The Doors                                                                             |
| Audioslave                                                                            |
| Stone Temple Pilots                                                                   |
| Sir Georg Solti & Wiener Philharmoniker                                               |
| Terry Bozzio, Tony Levin & Steve Stevens                                              |
| Raimundos                                                                             |
| Caetano Veloso                                                                        |
| Faith No More                                                                         |
| Toquinho & Vinícius                                                                   |
| Academy of St. Martin in the Fields & Sir Neville Marriner                            |
| Velvet Revolver                                                                       |
| London Symphony Orchestra & Sir Charles Mackerras                                     |
| Billy Cobham                                                                          |
| Chor der Wiener Staatsoper, Herbert Von Karajan & Wiener Philharmoniker               |
| Nirvana                                                                               |
| Martin Roscoe                                                                         |
| Otto Klemperer & Philharmonia Orchestra                                               |
| Mela Tenenbaum, Pro Musica Prague & Richard Kapp                                      |
| Christopher O'Riley                                                                   |
| Scorpions                                                                             |
| Dennis Chambers                                                                       |
| Adrian Leaper & Doreen de Feis                                                        |
| Antônio Carlos Jobim                                                                  |
| Britten Sinfonia, Ivor Bolton & Lesley Garrett                                        |
| Spyro Gyra                                                                            |
| Jimi Hendrix                                                                          |
| David Coverdale                                                                       |
| Fretwork                                                                              |
| Battlestar Galactica                                                                  |
| Gustav Mahler                                                                         |
| Wilhelm Kempff                                                                        |
| Foo Fighters                                                                          |
| Academy of St. Martin in the Fields, Sir Neville Marriner & Thurston Dart             |
| Michael Tilson Thomas & San Francisco Symphony                                        |
| Joe Satriani                                                                          |
| Kiss                                                                                  |
| Sir Georg Solti, Sumi Jo & Wiener Philharmoniker                                      |
| Luciano Pavarotti                                                                     |
| Calexico                                                                              |
| Apocalyptica                                                                          |
| Raul Seixas                                                                           |
| O Terço                                                                               |
| Herbert Von Karajan, Mirella Freni & Wiener Philharmoniker                            |
| Os Mutantes                                                                           |
| The Rolling Stones                                                                    |
| Hilary Hahn, Jeffrey Kahane, Los Angeles Chamber Orchestra & Margaret Batjer          |
| UB40                                                                                  |
| Led Zeppelin                                                                          |
| Deep Purple                                                                           |
| Def Leppard                                                                           |
| Jota Quest                                                                            |
| Aerosmith                                                                             |
| Titãs                                                                                 |
| Frank Zappa & Captain Beefheart                                                       |
| Aaron Goldberg                                                                        |
| Eric Clapton                                                                          |
| System Of A Down                                                                      |
| Edo de Waart & San Francisco Symphony                                                 |
| Planet Hemp                                                                           |
| Philip Glass Ensemble                                                                 |
| Paul D'Ianno                                                                          |
| Gene Krupa                                                                            |
| Cake                                                                                  |
| The Black Crowes                                                                      |
| The Police                                                                            |
| Emanuel Ax, Eugene Ormandy & Philadelphia Orchestra                                   |
| Funk Como Le Gusta                                                                    |
| Boston Symphony Orchestra & Seiji Ozawa                                               |
| Black Sabbath                                                                         |
| Alanis Morissette                                                                     |
| Iron Maiden                                                                           |
| Jorge Ben                                                                             |
| Metallica                                                                             |
| Men At Work                                                                           |
| Equale Brass Ensemble, John Eliot Gardiner & Munich Monteverdi Orchestra and Choir    |
| Red Hot Chili Peppers                                                                 |
| Page & Plant                                                                          |
| Heroes                                                                                |
| Cláudio Zoli                                                                          |
| Vinícius De Moraes                                                                    |
| Chris Cornell                                                                         |
| Richard Marlow & The Choir of Trinity College, Cambridge                              |
| Jamiroquai                                                                            |
| Habib Koité and Bamada                                                                |
| Gilberto Gil                                                                          |
| Berliner Philharmoniker & Hans Rosbaud                                                |
| Chicago Symphony Orchestra & Fritz Reiner                                             |
| Barry Wordsworth & BBC Concert Orchestra                                              |
| Berliner Philharmoniker & Herbert Von Karajan                                         |
| Berliner Philharmoniker, Claudio Abbado & Sabine Meyer                                |
| Mötley Crüe                                                                           |
| Black Label Society                                                                   |
| Maurizio Pollini                                                                      |
| James Brown                                                                           |
| James Levine                                                                          |
| Judas Priest                                                                          |
| The 12 Cellists of The Berlin Philharmonic                                            |
| Antal Doráti & London Symphony Orchestra                                              |
| Chicago Symphony Chorus, Chicago Symphony Orchestra & Sir Georg Solti                 |
| Creedence Clearwater Revival                                                          |
| Aisha Duo                                                                             |
| Djavan                                                                                |
| The Tea Party                                                                         |
| Falamansa                                                                             |
| Ed Motta                                                                              |
| Ton Koopman                                                                           |
| Yo-Yo Ma                                                                              |
| Sergei Prokofiev & Yuri Temirkanov                                                    |
| Santana                                                                               |
| U2                                                                                    |
| Scholars Baroque Ensemble                                                             |
| Felix Schmidt, London Symphony Orchestra & Rafael Frühbeck de Burgos                  |
| Aaron Copland & London Symphony Orchestra                                             |
| The Cult                                                                              |
| Motörhead                                                                             |
| Marillion                                                                             |
| Olodum                                                                                |
| Charles Dutoit & L'Orchestre Symphonique de Montréal                                  |
| Temple of the Dog                                                                     |
| Philharmonia Orchestra & Sir Neville Marriner                                         |
| Alice In Chains                                                                       |
| Accept                                                                                |
| Various Artists                                                                       |
| Julian Bream                                                                          |
| Ozzy Osbourne                                                                         |
| Marcos Valle                                                                          |
| Nash Ensemble                                                                         |
| Göteborgs Symfoniker & Neeme Järvi                                                    |
| Leonard Bernstein & New York Philharmonic                                             |
| Body Count                                                                            |
| House Of Pain                                                                         |
| Tim Maia                                                                              |
| Zeca Pagodinho                                                                        |
| Stevie Ray Vaughan & Double Trouble                                                   |
| The Clash                                                                             |
| Roger Norrington, London Classical Players                                            |
| C. Monteverdi, Nigel Rogers - Chiaroscuro; London Baroque; London Cornett & Sackbu    |
| Buddy Guy                                                                             |
| Choir Of Westminster Abbey & Simon Preston                                            |
| Lost                                                                                  |
| Orchestra of The Age of Enlightenment                                                 |
| Pearl Jam                                                                             |
| João Suplicy                                                                          |
| Passengers                                                                            |
| Karsh Kale                                                                            |
| The Who                                                                               |
| Anne-Sophie Mutter, Herbert Von Karajan & Wiener Philharmoniker                       |
| Green Day                                                                             |
| AC/DC                                                                                 |
| Legião Urbana                                                                         |
| Incognito                                                                             |
| Chico Buarque                                                                         |
| Yehudi Menuhin                                                                        |
| English Concert & Trevor Pinnock                                                      |
| Alberto Turco & Nova Schola Gregoriana                                                |
204 artists have recorded at least one album.

### 2. Artists Who Have No Recorded Album
```sql
SELECT DISTINCT
       ar.name AS artist_name
FROM artist ar
LEFT JOIN album ab
   ON ar.artist_id=ab.artist_id
WHERE ab.artist_id IS NULL;
```
```sql
SELECT DISTINCT
      ar.name AS artist_name
FROM album ab
RIGHT JOIN artist ar
   ON ab.artist_id=ar.artist_id
WHERE ab.artist_id IS NULL;
```  
71 artists have no recorded album. This means quite a number of artists in the database have no recorded albums.

### 3. Artists Who Have Recorded More Than One Album
```sql
SELECT DISTINCT
       ar.name AS artist_name
FROM artist ar
INNER JOIN album ab
   ON ar.artist_id=ab.artist_id
GROUP BY ar.artist_id,ab.artist_id,ar.name,ab.title
HAVING ab.artist_id > 1;
```
203 artists have recorded more than one album. Only one artist has recorded just one album.

### 4. Revenue by Genre
```sql
SELECT g.name AS genre_name,
       SUM(il.unit_price*il.quantity) AS total_revenue,
	   ROUND(SUM(il.unit_price*il.quantity)*100.0/SUM(SUM(il.unit_price*il.quantity))
	   OVER (),2) AS percentage
FROM invoice_line il
JOIN track t
   ON il.track_id=t.track_id
JOIN genre g
   ON t.genre_id=g.genre_id
GROUP BY g.genre_id, g.name
ORDER BY total_revenue DESC
LIMIT 20;
```
Revenue is concentrated among four of the 20 music genres. These genres play a significant role in the store's revenue performance.

### 5. Quantity Sold by Genre
```sql
SELECT g.name AS genre_name,
       SUM(il.quantity) AS total_quantity,
	   ROUND(SUM(il.quantity)*100.0/SUM(SUM(il.quantity))
	   OVER (),2) AS percentage
FROM invoice_line il
JOIN track t
   ON il.track_id=t.track_id
JOIN genre g
   ON t.genre_id=g.genre_id
GROUP BY g.genre_id, g.name
ORDER BY total_quantity DESC;
```
The four leading genres account for 77.19% of the total quantity sold and 73.50% of total sales value. This helps explain why they are the top revenue-generating genres.

### 6. Total Sales Value by Genre
```sql
SELECT g.name AS genre_name,
       SUM(il.unit_price) AS total_price,
	   ROUND(SUM(il.unit_price)*100.0/SUM(SUM(il.unit_price)) OVER (),2) AS percentage
FROM invoice_line il
JOIN track t
   ON il.track_id=t.track_id
JOIN genre g
   ON t.genre_id=g.genre_id
GROUP BY g.genre_id, g.name
ORDER BY total_price DESC;
```
The four leading genres contribute 73.50% of total sales value, showing that most of the store's sales value comes from these four genres.

### 7. Top Tracks in the Four Leading Genres
```sql
SELECT g.name AS genre_name,
       t.name AS track_name,
	   SUM(il.unit_price*il.quantity) AS total_revenue,
	   ROUND(SUM(il.unit_price*il.quantity)*100.0/SUM(SUM(il.unit_price*il.quantity))
	   OVER (),2) AS percentage
FROM genre g
JOIN track t
  ON g.genre_id=t.genre_id
JOIN invoice_line il
ON t.track_id=il.track_id
WHERE g.name IN ('Rock', 'Latin', 'Metal', 'Alternative & Punk' )
GROUP BY g.name, t.track_id, t.name
ORDER BY total_revenue DESC;
```
Some tracks within the other genres recorded higher individual revenue than tracks within the four leading genres. Despite this, the four leading genres generated more total revenue. This led me to investigate the number of tracks available in the top-performing genres compared with the other genres.

### 8. Top Tracks in the Other Genres
```sql
SELECT g.name AS genre_name,
       t.name AS track_name,
	   SUM(il.unit_price*il.quantity) AS total_revenue,
	   ROUND(SUM(il.unit_price*il.quantity)*100.0/SUM(SUM(il.unit_price*il.quantity))
	   OVER (),2) AS percentage
FROM genre g
JOIN track t
  ON g.genre_id=t.genre_id
JOIN invoice_line il
ON t.track_id=il.track_id
WHERE g.name NOT IN ('Rock', 'Latin', 'Metal', 'Alternative & Punk' )
GROUP BY g.name, t.track_id, t.name
ORDER BY total_revenue DESC;
```
Some tracks within the other genres recorded higher individual revenue values. However, this did not change the overall finding that the four leading genres generated more total revenue.

### 9. Number of Tracks in the Four Leading Genres
```sql
SELECT COUNT(t.name)
FROM genre g
JOIN track t
ON g.genre_id=t.genre_id
WHERE g.name IN ('Rock', 'Latin', 'Metal', 'Alternative & Punk');
```
The four leading genres contain 2,582 tracks, while the other genres contain 921 tracks. This shows that the leading genres make up a larger share of the store's music catalogue, which may help explain their strong revenue contribution.

### 10. Number of Tracks in the Other Genres
```sql
SELECT COUNT(t.name)
FROM genre g
JOIN track t
ON g.genre_id=t.genre_id
WHERE g.name NOT IN ('Rock', 'Latin', 'Metal', 'Alternative & Punk');
```
The other genres contain 921 tracks, compared with 2,582 tracks in the four leading genres. This shows that fewer tracks are available across the other genres.

## Query Results

[Add link to your screenshots folder here]







