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
| artist_name                                                                 |
|-----------------------------------------------------------------------------|
| Edson, DJ Marky & DJ Patife Featuring Fernanda Porto                        |
| Luiz Melodia                                                                |
| Santana Feat. Lauryn Hill & Cee-Lo                                          |
| Nação Zumbi                                                                 |
| Gustavo & Andres Veiga & Salazar                                            |
| Vinicius, Toquinho & Quarteto Em Cy                                         |
| Black Eyed Peas                                                             |
| Vinícius E Odette Lara                                                      |
| Fernanda Porto                                                              |
| Mundo Livre S/A                                                             |
| Sabotage E Instituto                                                        |
| Banda Black Rio                                                             |
| R.E.M. Feat. KRS-One                                                        |
| Jack Johnson                                                                |
| Peter Tosh                                                                  |
| Stereo Maracana                                                             |
| Los Lonely Boys                                                             |
| Nega Gizza                                                                  |
| Los Hermanos                                                                |
| Instituto                                                                   |
| Pedro Luís E A Parede                                                       |
| Avril Lavigne                                                               |
| Rodox                                                                       |
| Bebel Gilberto                                                              |
| Charlie Brown Jr.                                                           |
| Jackson Browne                                                              |
| Matisyahu                                                                   |
| Aerosmith & Sierra Leone's Refugee Allstars                                 |
| Santana Feat. Rob Thomas                                                    |
| Whitesnake                                                                  |
| Jack's Mannequin & Mick Fleetwood                                           |
| Jorge Vercilo                                                               |
| Os Cariocas                                                                 |
| Jaguares                                                                    |
| Vinícius De Moraes & Baden Powell                                           |
| DJ Dolores & Orchestra Santa Massa                                          |
| The Flaming Lips                                                            |
| Christina Aguilera featuring BigElf                                         |
| Ney Matogrosso                                                              |
| Nando Reis                                                                  |
| Santana Feat. Eric Clapton                                                  |
| Santana Feat. Maná                                                          |
| Corinne Bailey Rae                                                          |
| The Postal Service                                                          |
| Sandra De Sá                                                                |
| A Cor Do Som                                                                |
| Pedro Luís & A Parede                                                       |
| Youssou N'Dour                                                              |
| Barão Vermelho                                                              |
| Vinícius E Qurteto Em Cy                                                    |
| Kid Abelha                                                                  |
| Milton Nascimento & Bebeto                                                  |
| Otto                                                                        |
| Snow Patrol                                                                 |
| Santana Feat. The Project G&B                                               |
| Seu Jorge                                                                   |
| Academy of St. Martin in the Fields, Sir Neville Marriner & William Bennett |
| Simply Red                                                                  |
| João Gilberto                                                               |
| Xis                                                                         |
| Santana Feat. Everlast                                                      |
| Motörhead & Girlschool                                                      |
| Hermeto Pascoal                                                             |
| Santana Feat. Dave Matthews                                                 |
| Ben Harper                                                                  |
| Regina Spektor                                                              |
| Azymuth                                                                     |
| Dhani Harrison & Jakob Dylan                                                |
| Santana Feat. Eagle-Eye Cherry                                              |
| Big & Rich                                                                  |
| Baby Consuelo                                                               |

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
| artist_name                                                                           |
|---------------------------------------------------------------------------------------|
| O Rappa                                                                               |
| Miles Davis                                                                           |
| R.E.M.                                                                                |
| Lenny Kravitz                                                                         |
| Mônica Marianno                                                                       |
| Os Paralamas Do Sucesso                                                               |
| Chico Science & Nação Zumbi                                                           |
| Marisa Monte                                                                          |
| Itzhak Perlman                                                                        |
| Cássia Eller                                                                          |
| JET                                                                                   |
| Smashing Pumpkins                                                                     |
| The Posies                                                                            |
| Dread Zeppelin                                                                        |
| Frank Sinatra                                                                         |
| Soundgarden                                                                           |
| Orchestre Révolutionnaire et Romantique & John Eliot Gardiner                         |
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
| Bruce Dickinson                                                                       |
| Gerald Moore                                                                          |
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
| Scorpions                                                                             |
| Christopher O'Riley                                                                   |
| Dennis Chambers                                                                       |
| Adrian Leaper & Doreen de Feis                                                        |
| Antônio Carlos Jobim                                                                  |
| Spyro Gyra                                                                            |
| Britten Sinfonia, Ivor Bolton & Lesley Garrett                                        |
| Jimi Hendrix                                                                          |
| David Coverdale                                                                       |
| Fretwork                                                                              |
| Battlestar Galactica                                                                  |
| Gustav Mahler                                                                         |
| Wilhelm Kempff                                                                        |
| Foo Fighters                                                                          |
| Academy of St. Martin in the Fields, Sir Neville Marriner & Thurston Dart             |
| Joe Satriani                                                                          |
| Michael Tilson Thomas & San Francisco Symphony                                        |
| Kiss                                                                                  |
| Luciano Pavarotti                                                                     |
| Sir Georg Solti, Sumi Jo & Wiener Philharmoniker                                      |
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
| Paul D'Ianno                                                                          |
| Philip Glass Ensemble                                                                 |
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
| Judas Priest                                                                          |
| James Levine                                                                          |
| The 12 Cellists of The Berlin Philharmonic                                            |
| Creedence Clearwater Revival                                                          |
| Chicago Symphony Chorus, Chicago Symphony Orchestra & Sir Georg Solti                 |
| Antal Doráti & London Symphony Orchestra                                              |
| Aisha Duo                                                                             |
| Djavan                                                                                |
| Falamansa                                                                             |
| The Tea Party                                                                         |
| Ed Motta                                                                              |
| Ton Koopman                                                                           |
| Yo-Yo Ma                                                                              |
| Santana                                                                               |
| Sergei Prokofiev & Yuri Temirkanov                                                    |
| U2                                                                                    |
| Scholars Baroque Ensemble                                                             |
| Felix Schmidt, London Symphony Orchestra & Rafael Frühbeck de Burgos                  |
| Aaron Copland & London Symphony Orchestra                                             |
| The Cult                                                                              |
| Motörhead                                                                             |
| Marillion                                                                             |
| Olodum                                                                                |
| Temple of the Dog                                                                     |
| Charles Dutoit & L'Orchestre Symphonique de Montréal                                  |
| Philharmonia Orchestra & Sir Neville Marriner                                         |
| Alice In Chains                                                                       |
| Accept                                                                                |
| Various Artists                                                                       |
| Julian Bream                                                                          |
| Ozzy Osbourne                                                                         |
| Marcos Valle                                                                          |
| Göteborgs Symfoniker & Neeme Järvi                                                    |
| Nash Ensemble                                                                         |
| Leonard Bernstein & New York Philharmonic                                             |
| Body Count                                                                            |
| House Of Pain                                                                         |
| Tim Maia                                                                              |
| Zeca Pagodinho                                                                        |
| Stevie Ray Vaughan & Double Trouble                                                   |
| The Clash                                                                             |
| Roger Norrington, London Classical Players                                            |
| Buddy Guy                                                                             |
| C. Monteverdi, Nigel Rogers - Chiaroscuro; London Baroque; London Cornett & Sackbu    |
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
| Legião Urbana                                                                         |
| Incognito                                                                             |
| Chico Buarque                                                                         |
| Yehudi Menuhin                                                                        |
| English Concert & Trevor Pinnock                                                      |
| Alberto Turco & Nova Schola Gregoriana                                                |

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
| genre_name         | total_revenue | percentage |
|--------------------|---------------|------------|
| Rock               | 826.65        | 35.50      |
| Latin              | 382.14        | 16.41      |
| Metal              | 261.36        | 11.22      |
| Alternative & Punk | 241.56        | 10.37      |
| TV Shows           | 93.53         | 4.02       |
| Jazz               | 79.20         | 3.40       |
| Blues              | 60.39         | 2.59       |
| Drama              | 57.71         | 2.48       |
| R&B/Soul           | 40.59         | 1.74       |
| Classical          | 40.59         | 1.74       |
| Sci Fi & Fantasy   | 39.80         | 1.71       |
| Reggae             | 29.70         | 1.28       |
| Pop                | 27.72         | 1.19       |
| Soundtrack         | 19.80         | 0.85       |
| Comedy             | 17.91         | 0.77       |
| Hip Hop/Rap        | 16.83         | 0.72       |
| Bossa Nova         | 14.85         | 0.64       |
| Alternative        | 13.86         | 0.60       |
| World              | 12.87         | 0.55       |
| Science Fiction    | 11.94         | 0.51       |
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
| genre_name         | total_quantity | percentage |
|--------------------|----------------|------------|
| Rock               | 835            | 37.28      |
| Latin              | 386            | 17.23      |
| Metal              | 264            | 11.79      |
| Alternative & Punk | 244            | 10.89      |
| Jazz               | 80             | 3.57       |
| Blues              | 61             | 2.72       |
| TV Shows           | 47             | 2.10       |
| R&B/Soul           | 41             | 1.83       |
| Classical          | 41             | 1.83       |
| Reggae             | 30             | 1.34       |
| Drama              | 29             | 1.29       |
| Pop                | 28             | 1.25       |
| Sci Fi & Fantasy   | 20             | 0.89       |
| Soundtrack         | 20             | 0.89       |
| Hip Hop/Rap        | 17             | 0.76       |
| Bossa Nova         | 15             | 0.67       |
| Alternative        | 14             | 0.63       |
| World              | 13             | 0.58       |
| Heavy Metal        | 12             | 0.54       |
| Electronica/Dance  | 12             | 0.54       |
| Easy Listening     | 10             | 0.45       |
| Comedy             | 9              | 0.40       |
| Rock And Roll      | 6              | 0.27       |
| Science Fiction    | 6              | 0.27       |

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
| genre_name         | total_price | percentage |
|--------------------|-------------|------------|
| Rock               | 826.65      | 35.50      |
| Latin              | 382.14      | 16.41      |
| Metal              | 261.36      | 11.22      |
| Alternative & Punk | 241.56      | 10.37      |
| TV Shows           | 93.53       | 4.02       |
| Jazz               | 79.20       | 3.40       |
| Blues              | 60.39       | 2.59       |
| Drama              | 57.71       | 2.48       |
| R&B/Soul           | 40.59       | 1.74       |
| Classical          | 40.59       | 1.74       |
| Sci Fi & Fantasy   | 39.80       | 1.71       |
| Reggae             | 29.70       | 1.28       |
| Pop                | 27.72       | 1.19       |
| Soundtrack         | 19.80       | 0.85       |
| Comedy             | 17.91       | 0.77       |
| Hip Hop/Rap        | 16.83       | 0.72       |
| Bossa Nova         | 14.85       | 0.64       |
| Alternative        | 13.86       | 0.60       |
| World              | 12.87       | 0.55       |
| Science Fiction    | 11.94       | 0.51       |
| Heavy Metal        | 11.88       | 0.51       |
| Electronica/Dance  | 11.88       | 0.51       |
| Easy Listening     | 9.90        | 0.43       |
| Rock And Roll      | 5.94        | 0.26       |

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
| genre_name         | track_name                                                                                                                  | total_revenue | percentage |
|--------------------|-----------------------------------------------------------------------------------------------------------------------------|---------------|------------|
| Alternative & Punk | Gyroscope                                                                                                                   | 1.98          | 0.12       |
| Rock               | Dirty Day                                                                                                                   | 1.98          | 0.12       |
| Latin              | Lixo Do Mangue                                                                                                              | 1.98          | 0.12       |
| Alternative & Punk | Release                                                                                                                     | 1.98          | 0.12       |
| Latin              | Morena De Angola                                                                                                            | 1.98          | 0.12       |
| Latin              | Woman Of The World (Ao Vivo)                                                                                                | 1.98          | 0.12       |
| Latin              | Selvagem                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Times Like These                                                                                                            | 1.98          | 0.12       |
| Rock               | Down by the Sea                                                                                                             | 1.98          | 0.12       |
| Alternative & Punk | Take It Or Leave It                                                                                                         | 1.98          | 0.12       |
| Latin              | Bumbo Da Mangueira                                                                                                          | 1.98          | 0.12       |
| Latin              | A Novidade (Live)                                                                                                           | 1.98          | 0.12       |
| Alternative & Punk | Fall On Me                                                                                                                  | 1.98          | 0.12       |
| Rock               | Susie Q                                                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | Real Love                                                                                                                   | 1.98          | 0.12       |
| Metal              | Snowblind                                                                                                                   | 1.98          | 0.12       |
| Latin              | Bem Devagar                                                                                                                 | 1.98          | 0.12       |
| Latin              | As Rosas Não Falam (Beth Carvalho)                                                                                          | 1.98          | 0.12       |
| Alternative & Punk | So Central Rain                                                                                                             | 1.98          | 0.12       |
| Latin              | Saber Amar                                                                                                                  | 1.98          | 0.12       |
| Latin              | Falamansa Song                                                                                                              | 1.98          | 0.12       |
| Latin              | Nebulosa Do Amor                                                                                                            | 1.98          | 0.12       |
| Rock               | City Of Blinding Lights                                                                                                     | 1.98          | 0.12       |
| Rock               | Mr. Cab Driver                                                                                                              | 1.98          | 0.12       |
| Rock               | Living Loving Maid (She's Just A Woman)                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | Toda Cor                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Nice Guys Finish Last                                                                                                       | 1.98          | 0.12       |
| Metal              | Gangland                                                                                                                    | 1.98          | 0.12       |
| Metal              | Leper Messiah                                                                                                               | 1.98          | 0.12       |
| Rock               | Untitled                                                                                                                    | 1.98          | 0.12       |
| Latin              | Tempo Perdido                                                                                                               | 1.98          | 0.12       |
| Latin              | Stir It Up (Live)                                                                                                           | 1.98          | 0.12       |
| Rock               | Overdose                                                                                                                    | 1.98          | 0.12       |
| Rock               | Que Luz É Essa                                                                                                              | 1.98          | 0.12       |
| Rock               | Miami                                                                                                                       | 1.98          | 0.12       |
| Latin              | Só Tinha De Ser Com Você                                                                                                    | 1.98          | 0.12       |
| Metal              | Battery                                                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | Give Me Novacaine                                                                                                           | 1.98          | 0.12       |
| Rock               | For Your Life                                                                                                               | 1.98          | 0.12       |
| Latin              | Meu Caro Amigo                                                                                                              | 1.98          | 0.12       |
| Rock               | Eruption                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Whatsername                                                                                                                 | 1.98          | 0.12       |
| Latin              | Música No Ar                                                                                                                | 1.98          | 0.12       |
| Latin              | Menestrel Das Alagoas                                                                                                       | 1.98          | 0.12       |
| Rock               | Shock Me                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Saturnine                                                                                                                   | 1.98          | 0.12       |
| Latin              | L'Avventura                                                                                                                 | 1.98          | 0.12       |
| Latin              | Geni E O Zepelim                                                                                                            | 1.98          | 0.12       |
| Alternative & Punk | Waiting                                                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | Babylon                                                                                                                     | 1.98          | 0.12       |
| Rock               | Pride (In The Name Of Love)                                                                                                 | 1.98          | 0.12       |
| Metal              | For Whom The Bell Tolls                                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | When I Come Around                                                                                                          | 1.98          | 0.12       |
| Metal              | Turbo Lover                                                                                                                 | 1.98          | 0.12       |
| Rock               | Right On Time                                                                                                               | 1.98          | 0.12       |
| Alternative & Punk | Train In Vain                                                                                                               | 1.98          | 0.12       |
| Latin              | Samba Do Lado                                                                                                               | 1.98          | 0.12       |
| Metal              | Soldier Side - Intro                                                                                                        | 1.98          | 0.12       |
| Rock               | Undertow                                                                                                                    | 1.98          | 0.12       |
| Latin              | Mel                                                                                                                         | 1.98          | 0.12       |
| Rock               | Sunday Bloody Sunday                                                                                                        | 1.98          | 0.12       |
| Rock               | We Are The Champions                                                                                                        | 1.98          | 0.12       |
| Latin              | Samba De Orly                                                                                                               | 1.98          | 0.12       |
| Alternative & Punk | She Loves Me Not                                                                                                            | 1.98          | 0.12       |
| Metal              | Shoot Me Again                                                                                                              | 1.98          | 0.12       |
| Rock               | When I Look At The World                                                                                                    | 1.98          | 0.12       |
| Rock               | Hallelujah Here She Comes                                                                                                   | 1.98          | 0.12       |
| Rock               | Inject The Venom                                                                                                            | 1.98          | 0.12       |
| Latin              | Romance Ideal                                                                                                               | 1.98          | 0.12       |
| Rock               | Calling Dr. Love                                                                                                            | 1.98          | 0.12       |
| Alternative & Punk | Caffeine                                                                                                                    | 1.98          | 0.12       |
| Rock               | I'm Gonna Crawl                                                                                                             | 1.98          | 0.12       |
| Metal              | Violent Pornography                                                                                                         | 1.98          | 0.12       |
| Metal              | The House Jack Built                                                                                                        | 1.98          | 0.12       |
| Rock               | Sweet Hitch-Hiker                                                                                                           | 1.98          | 0.12       |
| Metal              | The Prisoner                                                                                                                | 1.98          | 0.12       |
| Latin              | Norwegian Wood                                                                                                              | 1.98          | 0.12       |
| Rock               | Two Hearts Beat As One                                                                                                      | 1.98          | 0.12       |
| Rock               | The Star Spangled Banner                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Cabeça Dinossauro                                                                                                           | 1.98          | 0.12       |
| Rock               | Dancing Days                                                                                                                | 1.98          | 0.12       |
| Metal              | Can I Play With Madness                                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | Last Cup Of Sorrow                                                                                                          | 1.98          | 0.12       |
| Rock               | Hallowed Be Thy Name                                                                                                        | 1.98          | 0.12       |
| Alternative & Punk | Esporrei Na Manivela                                                                                                        | 1.98          | 0.12       |
| Latin              | Is This Love (Live)                                                                                                         | 1.98          | 0.12       |
| Rock               | Sangue Latino                                                                                                               | 1.98          | 0.12       |
| Rock               | You Better You Bet                                                                                                          | 1.98          | 0.12       |
| Metal              | Phantom Lord                                                                                                                | 1.98          | 0.12       |
| Alternative & Punk | Untitled                                                                                                                    | 1.98          | 0.12       |
| Rock               | Year to the Day                                                                                                             | 1.98          | 0.12       |
| Alternative & Punk | Big Wave                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Lugar Nenhum                                                                                                                | 1.98          | 0.12       |
| Alternative & Punk | Bowels Of The Devil                                                                                                         | 1.98          | 0.12       |
| Rock               | Sun King                                                                                                                    | 1.98          | 0.12       |
| Metal              | Blood Brothers                                                                                                              | 1.98          | 0.12       |
| Rock               | Perfect Crime                                                                                                               | 1.98          | 0.12       |
| Latin              | Dois Pra Lá, Dois Pra Cá                                                                                                    | 1.98          | 0.12       |
| Rock               | For the Greater Good of God                                                                                                 | 1.98          | 0.12       |
| Latin              | Brasil                                                                                                                      | 1.98          | 0.12       |
| Rock               | You're My Best Friend                                                                                                       | 1.98          | 0.12       |
| Latin              | Açai                                                                                                                        | 1.98          | 0.12       |
| Alternative & Punk | Voodoo                                                                                                                      | 1.98          | 0.12       |
| Rock               | Walking Into Clarksdale                                                                                                     | 1.98          | 0.12       |
| Rock               | Snowballed                                                                                                                  | 1.98          | 0.12       |
| Rock               | Sure Know Something                                                                                                         | 1.98          | 0.12       |
| Latin              | Esquinas                                                                                                                    | 1.98          | 0.12       |
| Rock               | Judgement Of Heaven                                                                                                         | 1.98          | 0.12       |
| Latin              | Comportamento Geral                                                                                                         | 1.98          | 0.12       |
| Rock               | Maybe I'm A Leo                                                                                                             | 1.98          | 0.12       |
| Rock               | Living On Love                                                                                                              | 1.98          | 0.12       |
| Metal              | Aces High                                                                                                                   | 1.98          | 0.12       |
| Latin              | Azul                                                                                                                        | 1.98          | 0.12       |
| Rock               | Everlasting Love                                                                                                            | 1.98          | 0.12       |
| Rock               | Peace On Earth                                                                                                              | 1.98          | 0.12       |
| Latin              | Álibi                                                                                                                       | 1.98          | 0.12       |
| Rock               | Speed Of Light                                                                                                              | 1.98          | 0.12       |
| Rock               | Menino De Rua                                                                                                               | 1.98          | 0.12       |
| Rock               | Dazed and Confused                                                                                                          | 1.98          | 0.12       |
| Metal              | Children Of The Grave                                                                                                       | 1.98          | 0.12       |
| Metal              | Where Eagles Dare                                                                                                           | 1.98          | 0.12       |
| Latin              | Meu Erro                                                                                                                    | 1.98          | 0.12       |
| Metal              | Run Silent Run Deep                                                                                                         | 1.98          | 0.12       |
| Metal              | Re-Align                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Get Up                                                                                                                      | 1.98          | 0.12       |
| Alternative & Punk | Comida                                                                                                                      | 1.98          | 0.12       |
| Rock               | Not The Doctor                                                                                                              | 1.98          | 0.12       |
| Latin              | Tarde Em Itapoã                                                                                                             | 1.98          | 0.12       |
| Rock               | All Along The Watchtower                                                                                                    | 1.98          | 0.12       |
| Rock               | Flying High Again                                                                                                           | 1.98          | 0.12       |
| Rock               | Don't Look Now                                                                                                              | 1.98          | 0.12       |
| Latin              | Amor De Muito                                                                                                               | 1.98          | 0.12       |
| Alternative & Punk | Midlife Crisis                                                                                                              | 1.98          | 0.12       |
| Latin              | Pela Luz dos Olhos Teus (Miúcha e Tom Jobim)                                                                                | 1.98          | 0.12       |
| Rock               | No No No                                                                                                                    | 1.98          | 0.12       |
| Rock               | Deuces Are Wild                                                                                                             | 1.98          | 0.12       |
| Alternative & Punk | Cherub Rock                                                                                                                 | 1.98          | 0.12       |
| Alternative & Punk | Under The Bridge                                                                                                            | 1.98          | 0.12       |
| Rock               | Commotion                                                                                                                   | 1.98          | 0.12       |
| Metal              | Welcome Home (Sanitarium)                                                                                                   | 1.98          | 0.12       |
| Rock               | Sure Know Something                                                                                                         | 1.98          | 0.12       |
| Rock               | Tear                                                                                                                        | 1.98          | 0.12       |
| Rock               | Don't Look To The Eyes Of A Stranger                                                                                        | 1.98          | 0.12       |
| Metal              | You've Got Another Thing Comin'                                                                                             | 1.98          | 0.12       |
| Latin              | Mensagen De Amor (2000)                                                                                                     | 1.98          | 0.12       |
| Rock               | Mama, I'm Coming Home                                                                                                       | 1.98          | 0.12       |
| Alternative & Punk | Country Feedback                                                                                                            | 1.98          | 0.12       |
| Rock               | The Last Song                                                                                                               | 1.98          | 0.12       |
| Metal              | The Unforgiven II                                                                                                           | 1.98          | 0.12       |
| Metal              | Moonchild                                                                                                                   | 1.98          | 0.12       |
| Rock               | I'm Going Slightly Mad                                                                                                      | 1.98          | 0.12       |
| Metal              | Breakdown                                                                                                                   | 1.98          | 0.12       |
| Metal              | Whiskey In The Jar                                                                                                          | 1.98          | 0.12       |
| Rock               | Rock And Roll All Nite                                                                                                      | 1.98          | 0.12       |
| Rock               | Ramble On                                                                                                                   | 1.98          | 0.12       |
| Rock               | Sweetest Thing                                                                                                              | 1.98          | 0.12       |
| Rock               | The Thin Line Between Love & Hate                                                                                           | 1.98          | 0.12       |
| Latin              | Linha Do Equador                                                                                                            | 1.98          | 0.12       |
| Rock               | Walter's Walk                                                                                                               | 1.98          | 0.12       |
| Rock               | Good Golly Miss Molly                                                                                                       | 1.98          | 0.12       |
| Rock               | Piece Of Pie                                                                                                                | 1.98          | 0.12       |
| Rock               | Garden of Eden                                                                                                              | 1.98          | 0.12       |
| Latin              | Compadre                                                                                                                    | 1.98          | 0.12       |
| Metal              | Cornucopia                                                                                                                  | 1.98          | 0.12       |
| Alternative & Punk | Bullet With Butterfly Wings                                                                                                 | 1.98          | 0.12       |
| Rock               | The Garden                                                                                                                  | 1.98          | 0.12       |
| Rock               | In The Evening                                                                                                              | 1.98          | 0.12       |
| Rock               | Eruption                                                                                                                    | 1.98          | 0.12       |
| Rock               | The Number Of The Beast                                                                                                     | 1.98          | 0.12       |
| Rock               | Smoke On The Water                                                                                                          | 1.98          | 0.12       |
| Latin              | Mis Penas Lloraba Yo (Ao Vivo) Soy Gitano (Tangos)                                                                          | 1.98          | 0.12       |
| Latin              | Nossa Gente (Avisa Là)                                                                                                      | 1.98          | 0.12       |
| Alternative & Punk | I Believe                                                                                                                   | 1.98          | 0.12       |
| Latin              | Tanto Tempo                                                                                                                 | 1.98          | 0.12       |
| Rock               | The Trooper                                                                                                                 | 1.98          | 0.12       |
| Rock               | Somebody To Love                                                                                                            | 1.98          | 0.12       |
| Alternative & Punk | O Pulso                                                                                                                     | 1.98          | 0.12       |
| Alternative & Punk | Holiday                                                                                                                     | 1.98          | 0.12       |
| Rock               | Shakes and Ladders                                                                                                          | 1.98          | 0.12       |
| Alternative & Punk | Basket Case                                                                                                                 | 1.98          | 0.12       |
| Rock               | Bron-Y-Aur Stomp                                                                                                            | 1.98          | 0.12       |
| Rock               | The Midnight Special                                                                                                        | 1.98          | 0.12       |
| Rock               | What A Day                                                                                                                  | 1.98          | 0.12       |
| Metal              | Better Than You                                                                                                             | 1.98          | 0.12       |
| Rock               | How Many More Times                                                                                                         | 1.98          | 0.12       |
| Metal              | Motorbreath                                                                                                                 | 1.98          | 0.12       |
| Metal              | The Clairvoyant                                                                                                             | 1.98          | 0.12       |
| Rock               | Binky The Doormat                                                                                                           | 1.98          | 0.12       |
| Metal              | Nothing Else Matters                                                                                                        | 1.98          | 0.12       |
| Latin              | Beira Mar                                                                                                                   | 1.98          | 0.12       |
| Rock               | Balls to the Wall                                                                                                           | 1.98          | 0.12       |
| Rock               | Plaster Caster                                                                                                              | 1.98          | 0.12       |
| Rock               | War Pigs                                                                                                                    | 1.98          | 0.12       |
| Alternative & Punk | Easy                                                                                                                        | 1.98          | 0.12       |
| Rock               | The Aftermath                                                                                                               | 1.98          | 0.12       |
| Latin              | Revolta Olodum                                                                                                              | 1.98          | 0.12       |
| Rock               | Boris The Spider                                                                                                            | 1.98          | 0.12       |
| Metal              | Chemical Wedding                                                                                                            | 1.98          | 0.12       |
| Rock               | Pretty Noose                                                                                                                | 1.98          | 0.12       |
| Alternative & Punk | Heaven Coming Down                                                                                                          | 1.98          | 0.12       |
| Latin              | Meditação                                                                                                                   | 1.98          | 0.12       |
| Metal              | Stone Cold Crazy                                                                                                            | 1.98          | 0.12       |
| Metal              | Question!                                                                                                                   | 1.98          | 0.12       |
| Latin              | Não Quero Dinheiro                                                                                                          | 1.98          | 0.12       |
| Rock               | Whatever It Is, I Just Can't Stop                                                                                           | 1.98          | 0.12       |
| Rock               | Rocket Queen                                                                                                                | 1.98          | 0.12       |
| Alternative & Punk | Ando Meio Desligado                                                                                                         | 1.98          | 0.12       |
| Rock               | Folhas Secas                                                                                                                | 1.98          | 0.12       |
| Alternative & Punk | A Melhor Forma                                                                                                              | 1.98          | 0.12       |
| Rock               | Red Light                                                                                                                   | 1.98          | 0.12       |
| Latin              | Um Amor, Um Lugar                                                                                                           | 0.99          | 0.06       |
| Latin              | Caçador de Mim (Sá & Guarabyra)                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | Inside Job                                                                                                                  | 0.99          | 0.06       |
| Rock               | Smells Like Teen Spirit                                                                                                     | 0.99          | 0.06       |
| Metal              | Duelists                                                                                                                    | 0.99          | 0.06       |
| Latin              | Momentos Que Marcam                                                                                                         | 0.99          | 0.06       |
| Rock               | I Can't Quit You Baby(2)                                                                                                    | 0.99          | 0.06       |
| Rock               | Cold Gin                                                                                                                    | 0.99          | 0.06       |
| Metal              | Killing Floor                                                                                                               | 0.99          | 0.06       |
| Rock               | Spanish Eyes                                                                                                                | 0.99          | 0.06       |
| Latin              | Maracatu De Tiro Certeiro                                                                                                   | 0.99          | 0.06       |
| Latin              | Honolulu                                                                                                                    | 0.99          | 0.06       |
| Rock               | The Wake-Up Bomb                                                                                                            | 0.99          | 0.06       |
| Rock               | Be Good Johnny                                                                                                              | 0.99          | 0.06       |
| Rock               | Hang 'Em High                                                                                                               | 0.99          | 0.06       |
| Latin              | O Livro Dos Dias                                                                                                            | 0.99          | 0.06       |
| Latin              | Uma Brasileira                                                                                                              | 0.99          | 0.06       |
| Rock               | Walk On                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | 32 Dentes                                                                                                                   | 0.99          | 0.06       |
| Rock               | Wherever You May Go                                                                                                         | 0.99          | 0.06       |
| Metal              | Stranger in a Strange Land                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Chão De Estrelas                                                                                                            | 0.99          | 0.06       |
| Alternative & Punk | Nem 5 Minutos Guardados                                                                                                     | 0.99          | 0.06       |
| Rock               | The Day I Tried To Live                                                                                                     | 0.99          | 0.06       |
| Metal              | Dance                                                                                                                       | 0.99          | 0.06       |
| Latin              | Tempos Modernos                                                                                                             | 0.99          | 0.06       |
| Rock               | Night Of The Long Knives                                                                                                    | 0.99          | 0.06       |
| Rock               | Xanadu                                                                                                                      | 0.99          | 0.06       |
| Metal              | Tyrant (Live)                                                                                                               | 0.99          | 0.06       |
| Latin              | Xote Dos Milagres                                                                                                           | 0.99          | 0.06       |
| Rock               | Right Through You                                                                                                           | 0.99          | 0.06       |
| Metal              | Can I Play With Madness                                                                                                     | 0.99          | 0.06       |
| Latin              | Eclipse Oculto                                                                                                              | 0.99          | 0.06       |
| Rock               | Plaster Caster                                                                                                              | 0.99          | 0.06       |
| Rock               | Last Night On Earth                                                                                                         | 0.99          | 0.06       |
| Metal              | Mr. Crowley                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Wake Me Up When September Ends                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | The Morning After                                                                                                           | 0.99          | 0.06       |
| Rock               | Dazed and Confused                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Paint It Black                                                                                                              | 0.99          | 0.06       |
| Metal              | Blitzkrieg                                                                                                                  | 0.99          | 0.06       |
| Metal              | Hot Rockin'                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Talk About The Passion                                                                                                      | 0.99          | 0.06       |
| Metal              | Run To The Hilss                                                                                                            | 0.99          | 0.06       |
| Rock               | Goin' Blind                                                                                                                 | 0.99          | 0.06       |
| Latin              | Amor Demais                                                                                                                 | 0.99          | 0.06       |
| Metal              | My Friend Of Misery                                                                                                         | 0.99          | 0.06       |
| Latin              | Luis Inacio (300 Picaretas)                                                                                                 | 0.99          | 0.06       |
| Rock               | You Learn                                                                                                                   | 0.99          | 0.06       |
| Latin              | Água de Beber                                                                                                               | 0.99          | 0.06       |
| Rock               | Proud Mary                                                                                                                  | 0.99          | 0.06       |
| Latin              | Abrir A Porta                                                                                                               | 0.99          | 0.06       |
| Rock               | It's a Mistake                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Be Aggressive                                                                                                               | 0.99          | 0.06       |
| Metal              | Mama Said                                                                                                                   | 0.99          | 0.06       |
| Latin              | Refavela (Live)                                                                                                             | 0.99          | 0.06       |
| Metal              | Under The Sun/Every Day Comes and Goes                                                                                      | 0.99          | 0.06       |
| Rock               | Do You Love Me                                                                                                              | 0.99          | 0.06       |
| Rock               | Rag Doll                                                                                                                    | 0.99          | 0.06       |
| Rock               | Persuasion                                                                                                                  | 0.99          | 0.06       |
| Latin              | Entrando Na Sua (Intro)                                                                                                     | 0.99          | 0.06       |
| Latin              | Forty Days Instrumental                                                                                                     | 0.99          | 0.06       |
| Latin              | Feirinha da Pavuna/Luz do Repente/Bagaço da Laranja                                                                         | 0.99          | 0.06       |
| Latin              | Podres Poderes                                                                                                              | 0.99          | 0.06       |
| Latin              | Sem Sentido                                                                                                                 | 0.99          | 0.06       |
| Latin              | Copacabana (Live)                                                                                                           | 0.99          | 0.06       |
| Rock               | Fight From The Inside                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | Brain Stew                                                                                                                  | 0.99          | 0.06       |
| Rock               | Be Mine                                                                                                                     | 0.99          | 0.06       |
| Rock               | Anything Goes                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Era Uma Vez                                                                                                                 | 0.99          | 0.06       |
| Metal              | Tailgunner                                                                                                                  | 0.99          | 0.06       |
| Rock               | Whole Lotta Love (Medley)                                                                                                   | 0.99          | 0.06       |
| Latin              | Manuel                                                                                                                      | 0.99          | 0.06       |
| Rock               | Won't Get Fooled Again (Full Length Version)                                                                                | 0.99          | 0.06       |
| Alternative & Punk | Endgame                                                                                                                     | 0.99          | 0.06       |
| Metal              | The Assassin                                                                                                                | 0.99          | 0.06       |
| Rock               | Wake Up Dead Man                                                                                                            | 0.99          | 0.06       |
| Rock               | Fear Of The Dark                                                                                                            | 0.99          | 0.06       |
| Rock               | Sons Of Freedom                                                                                                             | 0.99          | 0.06       |
| Rock               | Get Out                                                                                                                     | 0.99          | 0.06       |
| Latin              | Menino Do Rio                                                                                                               | 0.99          | 0.06       |
| Rock               | Ali                                                                                                                         | 0.99          | 0.06       |
| Latin              | Sampa                                                                                                                       | 0.99          | 0.06       |
| Rock               | I'm A Boy                                                                                                                   | 0.99          | 0.06       |
| Metal              | King In Crimson                                                                                                             | 0.99          | 0.06       |
| Rock               | Lemon                                                                                                                       | 0.99          | 0.06       |
| Rock               | The Crunge                                                                                                                  | 0.99          | 0.06       |
| Rock               | Amazing                                                                                                                     | 0.99          | 0.06       |
| Rock               | Take The Power                                                                                                              | 0.99          | 0.06       |
| Latin              | Um Amor Puro                                                                                                                | 0.99          | 0.06       |
| Rock               | You Oughta Know                                                                                                             | 0.99          | 0.06       |
| Rock               | Primary                                                                                                                     | 0.99          | 0.06       |
| Latin              | Filho Maravilha                                                                                                             | 0.99          | 0.06       |
| Rock               | No Quarter                                                                                                                  | 0.99          | 0.06       |
| Rock               | The Three Sunrises                                                                                                          | 0.99          | 0.06       |
| Rock               | Strange Kind Of Woman                                                                                                       | 0.99          | 0.06       |
| Metal              | Damage Case                                                                                                                 | 0.99          | 0.06       |
| Rock               | All I Want Is You                                                                                                           | 0.99          | 0.06       |
| Rock               | Corduroy                                                                                                                    | 0.99          | 0.06       |
| Rock               | On Mercury                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Get What You Need                                                                                                           | 0.99          | 0.06       |
| Metal              | You Could Be Mine                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Suck My Kiss                                                                                                                | 0.99          | 0.06       |
| Rock               | Any Colour You Like                                                                                                         | 0.99          | 0.06       |
| Latin              | Vou Pra Ai                                                                                                                  | 0.99          | 0.06       |
| Latin              | Ela Disse Adeus                                                                                                             | 0.99          | 0.06       |
| Metal              | Ghost Of The Navigator                                                                                                      | 0.99          | 0.06       |
| Rock               | Dead And Bloated                                                                                                            | 0.99          | 0.06       |
| Latin              | Perplexo                                                                                                                    | 0.99          | 0.06       |
| Metal              | Shout At The Devil                                                                                                          | 0.99          | 0.06       |
| Metal              | Intro                                                                                                                       | 0.99          | 0.06       |
| Rock               | Immigrant Song                                                                                                              | 0.99          | 0.06       |
| Rock               | For Your Babies                                                                                                             | 0.99          | 0.06       |
| Rock               | High Ball Shooter                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Sua Impossivel Chance                                                                                                       | 0.99          | 0.06       |
| Latin              | Gota D'água                                                                                                                 | 0.99          | 0.06       |
| Rock               | Neworld                                                                                                                     | 0.99          | 0.06       |
| Latin              | I Feel Good (I Got You) - Sossego                                                                                           | 0.99          | 0.06       |
| Latin              | Manguetown                                                                                                                  | 0.99          | 0.06       |
| Rock               | Staring At The Sun                                                                                                          | 0.99          | 0.06       |
| Rock               | Elderly Woman Behind The Counter In A Small Town                                                                            | 0.99          | 0.06       |
| Rock               | God Of Thunder                                                                                                              | 0.99          | 0.06       |
| Metal              | Paranoid                                                                                                                    | 0.99          | 0.06       |
| Rock               | Lord of Light                                                                                                               | 0.99          | 0.06       |
| Latin              | Caleidoscópio                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Life Line                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Walking Wounded                                                                                                             | 0.99          | 0.06       |
| Rock               | Freedom For My People                                                                                                       | 0.99          | 0.06       |
| Latin              | Madalena                                                                                                                    | 0.99          | 0.06       |
| Rock               | Before You Accuse Me                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | (White Man) In Hammersmith Palais                                                                                           | 0.99          | 0.06       |
| Rock               | Action                                                                                                                      | 0.99          | 0.06       |
| Rock               | Message in a Bottle (new classic rock mix)                                                                                  | 0.99          | 0.06       |
| Rock               | Afraid To Shoot Strangers                                                                                                   | 0.99          | 0.06       |
| Rock               | No Way Back                                                                                                                 | 0.99          | 0.06       |
| Latin              | Santa Clara Clareou                                                                                                         | 0.99          | 0.06       |
| Rock               | You Can't Do it Right (With the One You Love)                                                                               | 0.99          | 0.06       |
| Rock               | Going Down / Highway Star                                                                                                   | 0.99          | 0.06       |
| Metal              | Wrathchild                                                                                                                  | 0.99          | 0.06       |
| Metal              | Rime of the Ancient Mariner                                                                                                 | 0.99          | 0.06       |
| Rock               | Houses Of The Holy                                                                                                          | 0.99          | 0.06       |
| Rock               | Over The Hills And Far Away                                                                                                 | 0.99          | 0.06       |
| Latin              | Sem Essa de Malandro Agulha                                                                                                 | 0.99          | 0.06       |
| Rock               | Leash                                                                                                                       | 0.99          | 0.06       |
| Metal              | Blackened                                                                                                                   | 0.99          | 0.06       |
| Rock               | Ramshackle Man                                                                                                              | 0.99          | 0.06       |
| Rock               | Silver And Gold                                                                                                             | 0.99          | 0.06       |
| Metal              | Bring Your Daughter... ...To The Slaughter                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Epic                                                                                                                        | 0.99          | 0.06       |
| Rock               | (Wish I Could) Hideaway                                                                                                     | 0.99          | 0.06       |
| Metal              | Fates Warning                                                                                                               | 0.99          | 0.06       |
| Rock               | Discotheque                                                                                                                 | 0.99          | 0.06       |
| Rock               | Since I've Been Loving You                                                                                                  | 0.99          | 0.06       |
| Latin              | E.C.T.                                                                                                                      | 0.99          | 0.06       |
| Metal              | The Unforgiven                                                                                                              | 0.99          | 0.06       |
| Rock               | All My Love                                                                                                                 | 0.99          | 0.06       |
| Rock               | Heaven Can Wait                                                                                                             | 0.99          | 0.06       |
| Rock               | Run To The Hills                                                                                                            | 0.99          | 0.06       |
| Metal              | Bored To Tears                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | White Riot                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Prá Dizer Adeus                                                                                                             | 0.99          | 0.06       |
| Rock               | Chaos-Control                                                                                                               | 0.99          | 0.06       |
| Rock               | New Test Leper                                                                                                              | 0.99          | 0.06       |
| Latin              | Gatas Extraordinárias                                                                                                       | 0.99          | 0.06       |
| Rock               | W.M.A.                                                                                                                      | 0.99          | 0.06       |
| Rock               | Funky Piano                                                                                                                 | 0.99          | 0.06       |
| Rock               | Pagan Baby                                                                                                                  | 0.99          | 0.06       |
| Rock               | Put The Finger On You                                                                                                       | 0.99          | 0.06       |
| Rock               | Stay (Faraway, So Close!)                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Pristina                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | It's The End Of The World As We Know It (And I Feel Fine)                                                                   | 0.99          | 0.06       |
| Rock               | Sam With The Showing Scalp Flat Top                                                                                         | 0.99          | 0.06       |
| Alternative & Punk | I Could Have Lied                                                                                                           | 0.99          | 0.06       |
| Latin              | Um Jantar Pra Dois                                                                                                          | 0.99          | 0.06       |
| Rock               | Hey Tonight                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Aeroplane Flies High                                                                                                        | 0.99          | 0.06       |
| Latin              | Vulcão Dub - Fui Eu                                                                                                         | 0.99          | 0.06       |
| Rock               | Your Time Is Gonna Come                                                                                                     | 0.99          | 0.06       |
| Rock               | Afraid To Shoot Strangers                                                                                                   | 0.99          | 0.06       |
| Metal              | Sweet Lady Luck                                                                                                             | 0.99          | 0.06       |
| Rock               | Stairway To Heaven                                                                                                          | 0.99          | 0.06       |
| Rock               | Coma                                                                                                                        | 0.99          | 0.06       |
| Rock               | Nobody's Home                                                                                                               | 0.99          | 0.06       |
| Rock               | Fortuneteller                                                                                                               | 0.99          | 0.06       |
| Rock               | Wrote A Song For Everyone                                                                                                   | 0.99          | 0.06       |
| Rock               | The Cut Runs Deep                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Poprocks And Coke                                                                                                           | 0.99          | 0.06       |
| Latin              | Quando Você Voltar                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Carnival Of Sorts                                                                                                           | 0.99          | 0.06       |
| Rock               | Black                                                                                                                       | 0.99          | 0.06       |
| Latin              | Óculos                                                                                                                      | 0.99          | 0.06       |
| Rock               | Scentless Apprentice                                                                                                        | 0.99          | 0.06       |
| Metal              | Back in the Village                                                                                                         | 0.99          | 0.06       |
| Metal              | The Beginning...At Last                                                                                                     | 0.99          | 0.06       |
| Latin              | Criança De Domingo                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | I Remember California                                                                                                       | 0.99          | 0.06       |
| Latin              | Minha Historia                                                                                                              | 0.99          | 0.06       |
| Rock               | I Belong To You                                                                                                             | 0.99          | 0.06       |
| Rock               | Go Down                                                                                                                     | 0.99          | 0.06       |
| Rock               | Murders In The Rue Morgue                                                                                                   | 0.99          | 0.06       |
| Rock               | Live and Let Die                                                                                                            | 0.99          | 0.06       |
| Alternative & Punk | Home Sick Home                                                                                                              | 0.99          | 0.06       |
| Rock               | Most High                                                                                                                   | 0.99          | 0.06       |
| Rock               | Todo Mundo Explica                                                                                                          | 0.99          | 0.06       |
| Rock               | Dead Horse                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Geek Stink Breath                                                                                                           | 0.99          | 0.06       |
| Rock               | Spank Thru                                                                                                                  | 0.99          | 0.06       |
| Latin              | Pais E Filhos                                                                                                               | 0.99          | 0.06       |
| Rock               | Twentienth Century Fox                                                                                                      | 0.99          | 0.06       |
| Metal              | Last Caress/Green Hell                                                                                                      | 0.99          | 0.06       |
| Latin              | Diga Lá, Coração                                                                                                            | 0.99          | 0.06       |
| Rock               | If God Will Send His Angels                                                                                                 | 0.99          | 0.06       |
| Rock               | Flash                                                                                                                       | 0.99          | 0.06       |
| Rock               | Dream Of Mirrors                                                                                                            | 0.99          | 0.06       |
| Alternative & Punk | Minority                                                                                                                    | 0.99          | 0.06       |
| Rock               | Angel                                                                                                                       | 0.99          | 0.06       |
| Rock               | It's A Hard Life                                                                                                            | 0.99          | 0.06       |
| Metal              | Fade To Black                                                                                                               | 0.99          | 0.06       |
| Rock               | De Do Do Do, De Da Da Da                                                                                                    | 0.99          | 0.06       |
| Latin              | Paisagem Na Janela                                                                                                          | 0.99          | 0.06       |
| Latin              | Principiando/Decolagem                                                                                                      | 0.99          | 0.06       |
| Metal              | Dee                                                                                                                         | 0.99          | 0.06       |
| Rock               | Under My Thumb                                                                                                              | 0.99          | 0.06       |
| Latin              | Começaria Tudo Outra Vez                                                                                                    | 0.99          | 0.06       |
| Rock               | Right Now                                                                                                                   | 0.99          | 0.06       |
| Metal              | The Thing That Should Not Be                                                                                                | 0.99          | 0.06       |
| Metal              | De Ja Vu                                                                                                                    | 0.99          | 0.06       |
| Rock               | Dark Corners                                                                                                                | 0.99          | 0.06       |
| Metal              | Iron Man                                                                                                                    | 0.99          | 0.06       |
| Metal              | Estranged                                                                                                                   | 0.99          | 0.06       |
| Metal              | The Trooper                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Domingo                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | From Out Of Nowhere                                                                                                         | 0.99          | 0.06       |
| Latin              | Texto "Verdade Tropical"                                                                                                    | 0.99          | 0.06       |
| Metal              | Breadfan                                                                                                                    | 0.99          | 0.06       |
| Latin              | O Cidadão Do Mundo                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Blissed & Gone                                                                                                              | 0.99          | 0.06       |
| Rock               | How The West Was Won And Where It Got Us                                                                                    | 0.99          | 0.06       |
| Latin              | Eu Vim Da Bahia - Live                                                                                                      | 0.99          | 0.06       |
| Metal              | Poor Twisted Me                                                                                                             | 0.99          | 0.06       |
| Rock               | One Man's Meat                                                                                                              | 0.99          | 0.06       |
| Rock               | Achilles Last Stand                                                                                                         | 0.99          | 0.06       |
| Rock               | My Hero                                                                                                                     | 0.99          | 0.06       |
| Rock               | Given To Fly                                                                                                                | 0.99          | 0.06       |
| Rock               | Fica                                                                                                                        | 0.99          | 0.06       |
| Rock               | Love Comes                                                                                                                  | 0.99          | 0.06       |
| Rock               | Spoonman                                                                                                                    | 0.99          | 0.06       |
| Latin              | Assim Caminha A Humanidade                                                                                                  | 0.99          | 0.06       |
| Rock               | Fairies Wear Boots                                                                                                          | 0.99          | 0.06       |
| Metal              | Now You're Gone                                                                                                             | 0.99          | 0.06       |
| Latin              | Zeca Violeiro                                                                                                               | 0.99          | 0.06       |
| Latin              | Mangueira                                                                                                                   | 0.99          | 0.06       |
| Latin              | De Ouro E Marfim (Live)                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Can't Get There From Here                                                                                                   | 0.99          | 0.06       |
| Rock               | Love Conquers All                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Drown                                                                                                                       | 0.99          | 0.06       |
| Rock               | Celebration Day                                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | If You Have To Ask                                                                                                          | 0.99          | 0.06       |
| Rock               | Four Sticks                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Posso Perder Minha Mulher, Minha Mãe, Desde Que Eu Tenha O Rock And Roll                                                    | 0.99          | 0.06       |
| Latin              | Samba Do Jato                                                                                                               | 0.99          | 0.06       |
| Rock               | Sapato 36                                                                                                                   | 0.99          | 0.06       |
| Latin              | Uns Dias                                                                                                                    | 0.99          | 0.06       |
| Rock               | The Evil That Men Do                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Body Count Anthem                                                                                                           | 0.99          | 0.06       |
| Rock               | Put Your Lights On                                                                                                          | 0.99          | 0.06       |
| Rock               | Um Dia Qualquer                                                                                                             | 0.99          | 0.06       |
| Rock               | By The Way                                                                                                                  | 0.99          | 0.06       |
| Rock               | No One Came                                                                                                                 | 0.99          | 0.06       |
| Rock               | Wake Up                                                                                                                     | 0.99          | 0.06       |
| Latin              | Lindo Lago Do Amor                                                                                                          | 0.99          | 0.06       |
| Rock               | You Got Me Rocking                                                                                                          | 0.99          | 0.06       |
| Rock               | Água E Fogo                                                                                                                 | 0.99          | 0.06       |
| Latin              | Aquele Abraço                                                                                                               | 0.99          | 0.06       |
| Rock               | Hey Joe                                                                                                                     | 0.99          | 0.06       |
| Rock               | Territorial Pissings                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | St. Jimmy                                                                                                                   | 0.99          | 0.06       |
| Rock               | Razor                                                                                                                       | 0.99          | 0.06       |
| Rock               | I Can't Quit You Baby                                                                                                       | 0.99          | 0.06       |
| Latin              | Mateus Enter                                                                                                                | 0.99          | 0.06       |
| Latin              | Voce Nao Entende Nada - Cotidiano                                                                                           | 0.99          | 0.06       |
| Rock               | You Shook Me                                                                                                                | 0.99          | 0.06       |
| Rock               | The Unwritten Law                                                                                                           | 0.99          | 0.06       |
| Rock               | Don't You Cry                                                                                                               | 0.99          | 0.06       |
| Latin              | O Amor Nao Sabe Esperar                                                                                                     | 0.99          | 0.06       |
| Rock               | Corinna                                                                                                                     | 0.99          | 0.06       |
| Latin              | Sobremesa                                                                                                                   | 0.99          | 0.06       |
| Rock               | The Unforgettable Fire                                                                                                      | 0.99          | 0.06       |
| Metal              | Still Of The Night                                                                                                          | 0.99          | 0.06       |
| Rock               | Mundaréu                                                                                                                    | 0.99          | 0.06       |
| Rock               | Black Dog                                                                                                                   | 0.99          | 0.06       |
| Latin              | Bye, Bye Brasil                                                                                                             | 0.99          | 0.06       |
| Rock               | Hats Off To (Roy) Harper                                                                                                    | 0.99          | 0.06       |
| Metal              | 2 Minutes To Midnight                                                                                                       | 0.99          | 0.06       |
| Rock               | I Need Love                                                                                                                 | 0.99          | 0.06       |
| Latin              | Tradição                                                                                                                    | 0.99          | 0.06       |
| Metal              | The Number Of The Beast                                                                                                     | 0.99          | 0.06       |
| Rock               | Fool In The Rain                                                                                                            | 0.99          | 0.06       |
| Rock               | These Colours Don't Run                                                                                                     | 0.99          | 0.06       |
| Latin              | Pela Internet (Live)                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Don't Go Back To Rockville                                                                                                  | 0.99          | 0.06       |
| Latin              | Indios                                                                                                                      | 0.99          | 0.06       |
| Rock               | Cathedral                                                                                                                   | 0.99          | 0.06       |
| Rock               | Hallowed Be Thy Name                                                                                                        | 0.99          | 0.06       |
| Rock               | Roxanne                                                                                                                     | 0.99          | 0.06       |
| Metal              | Ram It Down                                                                                                                 | 0.99          | 0.06       |
| Latin              | Canário Do Reino                                                                                                            | 0.99          | 0.06       |
| Latin              | Medo De Escuro                                                                                                              | 0.99          | 0.06       |
| Metal              | Book Of Thel                                                                                                                | 0.99          | 0.06       |
| Latin              | Primavera                                                                                                                   | 0.99          | 0.06       |
| Metal              | Evil Woman                                                                                                                  | 0.99          | 0.06       |
| Rock               | Hey Cisco                                                                                                                   | 0.99          | 0.06       |
| Rock               | You Keep On Moving                                                                                                          | 0.99          | 0.06       |
| Rock               | Get On Top                                                                                                                  | 0.99          | 0.06       |
| Rock               | Babyface                                                                                                                    | 0.99          | 0.06       |
| Rock               | Just Ain't Good Enough                                                                                                      | 0.99          | 0.06       |
| Metal              | Smokin' in The Boys Room                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Stuck With Me                                                                                                               | 0.99          | 0.06       |
| Metal              | ...And Justice For All                                                                                                      | 0.99          | 0.06       |
| Rock               | Radio GA GA                                                                                                                 | 0.99          | 0.06       |
| Rock               | Secrets                                                                                                                     | 0.99          | 0.06       |
| Rock               | Arc                                                                                                                         | 0.99          | 0.06       |
| Metal              | The Unforgiven                                                                                                              | 0.99          | 0.06       |
| Rock               | Hawkmoon 269                                                                                                                | 0.99          | 0.06       |
| Latin              | Giz                                                                                                                         | 0.99          | 0.06       |
| Latin              | Mistério da Raça                                                                                                            | 0.99          | 0.06       |
| Rock               | We Will Rock You                                                                                                            | 0.99          | 0.06       |
| Rock               | Forgiven                                                                                                                    | 0.99          | 0.06       |
| Rock               | Bad                                                                                                                         | 0.99          | 0.06       |
| Rock               | The Wicker Man                                                                                                              | 0.99          | 0.06       |
| Rock               | Welcome to the Jungle                                                                                                       | 0.99          | 0.06       |
| Latin              | Protesto Do Olodum (Ao Vivo)                                                                                                | 0.99          | 0.06       |
| Rock               | Go                                                                                                                          | 0.99          | 0.06       |
| Latin              | Life During Wartime                                                                                                         | 0.99          | 0.06       |
| Latin              | Seu Balancê                                                                                                                 | 0.99          | 0.06       |
| Rock               | If You Don't Know Me By Now                                                                                                 | 0.99          | 0.06       |
| Metal              | Same Ol' Situation                                                                                                          | 0.99          | 0.06       |
| Latin              | Preciso Apender a Viver Só (Maysa)                                                                                          | 0.99          | 0.06       |
| Rock               | Hands All Over                                                                                                              | 0.99          | 0.06       |
| Rock               | Love Is Strong                                                                                                              | 0.99          | 0.06       |
| Latin              | Casa no Campo                                                                                                               | 0.99          | 0.06       |
| Rock               | Dirty Little Thing                                                                                                          | 0.99          | 0.06       |
| Metal              | Trupets Of Jericho                                                                                                          | 0.99          | 0.06       |
| Metal              | A.N.D.R.O.T.A.Z.                                                                                                            | 0.99          | 0.06       |
| Metal              | The Wait                                                                                                                    | 0.99          | 0.06       |
| Latin              | Fora Da Ordem                                                                                                               | 0.99          | 0.06       |
| Rock               | Black Hole Sun                                                                                                              | 0.99          | 0.06       |
| Rock               | Atomic Punk                                                                                                                 | 0.99          | 0.06       |
| Metal              | N.I.B.                                                                                                                      | 0.99          | 0.06       |
| Rock               | The Great Gig In The Sky                                                                                                    | 0.99          | 0.06       |
| Latin              | Cinema Mudo                                                                                                                 | 0.99          | 0.06       |
| Rock               | Cotton Fields                                                                                                               | 0.99          | 0.06       |
| Latin              | New Love                                                                                                                    | 0.99          | 0.06       |
| Rock               | See You                                                                                                                     | 0.99          | 0.06       |
| Rock               | Dirty Water Dog                                                                                                             | 0.99          | 0.06       |
| Metal              | Running Free                                                                                                                | 0.99          | 0.06       |
| Latin              | Maria Rosa                                                                                                                  | 0.99          | 0.06       |
| Latin              | Sozinho (Hitmakers Classic Mix)                                                                                             | 0.99          | 0.06       |
| Latin              | Brumário                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Severed Hand                                                                                                                | 0.99          | 0.06       |
| Rock               | Born On The Bayou                                                                                                           | 0.99          | 0.06       |
| Rock               | One                                                                                                                         | 0.99          | 0.06       |
| Latin              | Avisa                                                                                                                       | 0.99          | 0.06       |
| Rock               | Cochise                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Paths Of Glory                                                                                                              | 0.99          | 0.06       |
| Rock               | I Was Made For Loving You                                                                                                   | 0.99          | 0.06       |
| Metal              | Ain't My Bitch                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | American Idiot                                                                                                              | 0.99          | 0.06       |
| Latin              | Maracatu Atômico [Trip Hop]                                                                                                 | 0.99          | 0.06       |
| Rock               | New Year's Day                                                                                                              | 0.99          | 0.06       |
| Rock               | The Zephyr Song                                                                                                             | 0.99          | 0.06       |
| Latin              | Grito De Alerta                                                                                                             | 0.99          | 0.06       |
| Rock               | Smells Like Teen Spirit                                                                                                     | 0.99          | 0.06       |
| Latin              | Nosso Adeus                                                                                                                 | 0.99          | 0.06       |
| Rock               | Pictures Of Home                                                                                                            | 0.99          | 0.06       |
| Rock               | Angel Of Harlem                                                                                                             | 0.99          | 0.06       |
| Rock               | Polly                                                                                                                       | 0.99          | 0.06       |
| Latin              | Quase Um Segundo                                                                                                            | 0.99          | 0.06       |
| Metal              | King Nothing                                                                                                                | 0.99          | 0.06       |
| Metal              | Fast And Loose                                                                                                              | 0.99          | 0.06       |
| Rock               | Finding My Way                                                                                                              | 0.99          | 0.06       |
| Rock               | Innuendo                                                                                                                    | 0.99          | 0.06       |
| Latin              | A Bencao E Outros                                                                                                           | 0.99          | 0.06       |
| Rock               | Born To Move                                                                                                                | 0.99          | 0.06       |
| Latin              | Encontrar Alguém                                                                                                            | 0.99          | 0.06       |
| Latin              | Esse Cara                                                                                                                   | 0.99          | 0.06       |
| Latin              | Não Sei O Que Eu Quero Da Vida                                                                                              | 0.99          | 0.06       |
| Metal              | B.Y.O.B.                                                                                                                    | 0.99          | 0.06       |
| Latin              | Coração do Agreste (Fafá de Belém)                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Waiting On A Sign                                                                                                           | 0.99          | 0.06       |
| Latin              | Trocando Em Miúdos                                                                                                          | 0.99          | 0.06       |
| Rock               | Walking After You                                                                                                           | 0.99          | 0.06       |
| Rock               | Advance Romance                                                                                                             | 0.99          | 0.06       |
| Metal              | Wild Side                                                                                                                   | 0.99          | 0.06       |
| Latin              | Agora Que O Dia Acordou                                                                                                     | 0.99          | 0.06       |
| Rock               | God Part II                                                                                                                 | 0.99          | 0.06       |
| Rock               | Baba O'Riley                                                                                                                | 0.99          | 0.06       |
| Latin              | Rios Pontes & Overdrives                                                                                                    | 0.99          | 0.06       |
| Rock               | Join Together                                                                                                               | 0.99          | 0.06       |
| Latin              | Música Urbana 2                                                                                                             | 0.99          | 0.06       |
| Rock               | Slither                                                                                                                     | 0.99          | 0.06       |
| Rock               | Lords of Karma                                                                                                              | 0.99          | 0.06       |
| Latin              | Salve Nossa Senhora                                                                                                         | 0.99          | 0.06       |
| Latin              | Ponta de Areia                                                                                                              | 0.99          | 0.06       |
| Rock               | Since I've Been Loving You                                                                                                  | 0.99          | 0.06       |
| Rock               | Sweethearts Together                                                                                                        | 0.99          | 0.06       |
| Latin              | Eu Apenas Queria Que Voçê Soubesse                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Letterbomb                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Doesn't Remind Me                                                                                                           | 0.99          | 0.06       |
| Rock               | Who'll Stop The Rain                                                                                                        | 0.99          | 0.06       |
| Rock               | River Song                                                                                                                  | 0.99          | 0.06       |
| Rock               | Down Under                                                                                                                  | 0.99          | 0.06       |
| Rock               | Sign Of The Cross                                                                                                           | 0.99          | 0.06       |
| Rock               | As Profecias                                                                                                                | 0.99          | 0.06       |
| Latin              | Me Liga                                                                                                                     | 0.99          | 0.06       |
| Latin              | Bora-Bora                                                                                                                   | 0.99          | 0.06       |
| Rock               | New Year's Day                                                                                                              | 0.99          | 0.06       |
| Latin              | As Dores do Mundo                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | The Wrong Child                                                                                                             | 0.99          | 0.06       |
| Latin              | Salve Simpatia                                                                                                              | 0.99          | 0.06       |
| Rock               | Sabbath, Bloody Sabbath                                                                                                     | 0.99          | 0.06       |
| Rock               | Saint Of Me                                                                                                                 | 0.99          | 0.06       |
| Rock               | Dazed And Confused                                                                                                          | 0.99          | 0.06       |
| Latin              | Casa                                                                                                                        | 0.99          | 0.06       |
| Rock               | Comin' Home                                                                                                                 | 0.99          | 0.06       |
| Rock               | A Kind Of Magic                                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | Família                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Infeliz Natal                                                                                                               | 0.99          | 0.06       |
| Rock               | Magic Bus                                                                                                                   | 0.99          | 0.06       |
| Rock               | Evil Walks                                                                                                                  | 0.99          | 0.06       |
| Latin              | Verdade                                                                                                                     | 0.99          | 0.06       |
| Latin              | Samba da Bençaco                                                                                                            | 0.99          | 0.06       |
| Metal              | Tomorrow's Dream                                                                                                            | 0.99          | 0.06       |
| Rock               | Everlong                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Amanhã Não Se Sabe                                                                                                          | 0.99          | 0.06       |
| Rock               | It's Late                                                                                                                   | 0.99          | 0.06       |
| Rock               | The Last Remaining Light                                                                                                    | 0.99          | 0.06       |
| Rock               | Trampled Under Foot                                                                                                         | 0.99          | 0.06       |
| Metal              | 14 Years                                                                                                                    | 0.99          | 0.06       |
| Latin              | Olodum - Smile (Instrumental)                                                                                               | 0.99          | 0.06       |
| Rock               | Another One Bites The Dust                                                                                                  | 0.99          | 0.06       |
| Rock               | One Step Closer                                                                                                             | 0.99          | 0.06       |
| Rock               | Mr. Brownstone                                                                                                              | 0.99          | 0.06       |
| Metal              | The Frayed Ends Of Sanity                                                                                                   | 0.99          | 0.06       |
| Rock               | Freewill                                                                                                                    | 0.99          | 0.06       |
| Metal              | The Wicker Man                                                                                                              | 0.99          | 0.06       |
| Rock               | Double Talkin' Jive                                                                                                         | 0.99          | 0.06       |
| Rock               | Happy Jack                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Cuyahoga                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | A Statistic                                                                                                                 | 0.99          | 0.06       |
| Rock               | Are You Gonna Go My Way                                                                                                     | 0.99          | 0.06       |
| Rock               | D'Yer Mak'er                                                                                                                | 0.99          | 0.06       |
| Rock               | Dreams                                                                                                                      | 0.99          | 0.06       |
| Rock               | Drifter                                                                                                                     | 0.99          | 0.06       |
| Rock               | Ozone Baby                                                                                                                  | 0.99          | 0.06       |
| Rock               | Hard Luck Woman                                                                                                             | 0.99          | 0.06       |
| Metal              | My World                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Rock The Casbah                                                                                                             | 0.99          | 0.06       |
| Rock               | Black Diamond                                                                                                               | 0.99          | 0.06       |
| Rock               | Stormbringer                                                                                                                | 0.99          | 0.06       |
| Metal              | (Anesthesia) Pulling Teeth                                                                                                  | 0.99          | 0.06       |
| Latin              | Aloha                                                                                                                       | 0.99          | 0.06       |
| Latin              | Não Vou Ficar                                                                                                               | 0.99          | 0.06       |
| Metal              | 2 Minutes To Midnight                                                                                                       | 0.99          | 0.06       |
| Rock               | The Number Of The Beast                                                                                                     | 0.99          | 0.06       |
| Rock               | Jump                                                                                                                        | 0.99          | 0.06       |
| Metal              | Master Of Puppets                                                                                                           | 0.99          | 0.06       |
| Latin              | Smells Like Teen Spirit (Ao Vivo)                                                                                           | 0.99          | 0.06       |
| Rock               | Communication Breakdown                                                                                                     | 0.99          | 0.06       |
| Rock               | The Wanderer                                                                                                                | 0.99          | 0.06       |
| Metal              | Low Man's Lyric                                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | Disenchanted Lullaby                                                                                                        | 0.99          | 0.06       |
| Rock               | I Still Haven't Found What I'm Looking For                                                                                  | 0.99          | 0.06       |
| Metal              | All Within My Hands                                                                                                         | 0.99          | 0.06       |
| Metal              | Attitude                                                                                                                    | 0.99          | 0.06       |
| Rock               | The Invisible Man                                                                                                           | 0.99          | 0.06       |
| Rock               | Heart Of Lothian: Wide Boy / Curtain Call                                                                                   | 0.99          | 0.06       |
| Rock               | Carouselambra                                                                                                               | 0.99          | 0.06       |
| Rock               | Right Next Door to Hell                                                                                                     | 0.99          | 0.06       |
| Latin              | Saudosismo                                                                                                                  | 0.99          | 0.06       |
| Latin              | Meu Guarda-Chuva                                                                                                            | 0.99          | 0.06       |
| Rock               | Californication                                                                                                             | 0.99          | 0.06       |
| Latin              | Garota de Ipanema (Dick Farney)                                                                                             | 0.99          | 0.06       |
| Rock               | Burden In My Hand                                                                                                           | 0.99          | 0.06       |
| Metal              | So What                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Malpractice                                                                                                                 | 0.99          | 0.06       |
| Rock               | Deuce                                                                                                                       | 0.99          | 0.06       |
| Metal              | The Small Hours                                                                                                             | 0.99          | 0.06       |
| Latin              | Carolina                                                                                                                    | 0.99          | 0.06       |
| Rock               | Suzie-Q, Pt. 2                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Radio Song                                                                                                                  | 0.99          | 0.06       |
| Rock               | Cascades : I'm Not Your Lover                                                                                               | 0.99          | 0.06       |
| Latin              | Faixa Amarela                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Disarm                                                                                                                      | 0.99          | 0.06       |
| Rock               | Zooropa                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Soot & Stars                                                                                                                | 0.99          | 0.06       |
| Latin              | Leila                                                                                                                       | 0.99          | 0.06       |
| Rock               | Man With The Woman Head                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Insensível                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Gone                                                                                                                        | 0.99          | 0.06       |
| Metal              | The Alchemist                                                                                                               | 0.99          | 0.06       |
| Latin              | Linha Do Equador                                                                                                            | 0.99          | 0.06       |
| Rock               | A Man And A Woman                                                                                                           | 0.99          | 0.06       |
| Rock               | Blow Your Mind                                                                                                              | 0.99          | 0.06       |
| Metal              | Powerslave                                                                                                                  | 0.99          | 0.06       |
| Metal              | Crash Course In Brain Surgery                                                                                               | 0.99          | 0.06       |
| Rock               | You Ain't the First                                                                                                         | 0.99          | 0.06       |
| Latin              | Saudosa Maloca                                                                                                              | 0.99          | 0.06       |
| Latin              | Manguetown                                                                                                                  | 0.99          | 0.06       |
| Rock               | Maria Maria                                                                                                                 | 0.99          | 0.06       |
| Metal              | The God That Failed                                                                                                         | 0.99          | 0.06       |
| Rock               | Don't Damn Me                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Boulevard Of Broken Dreams                                                                                                  | 0.99          | 0.06       |
| Rock               | Wrathchild                                                                                                                  | 0.99          | 0.06       |
| Rock               | The Wind Cries Mary                                                                                                         | 0.99          | 0.06       |
| Metal              | Pretty Tied Up                                                                                                              | 0.99          | 0.06       |
| Rock               | Departure                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Walking Contradiction                                                                                                       | 0.99          | 0.06       |
| Latin              | Lilás                                                                                                                       | 0.99          | 0.06       |
| Rock               | Get Off Of My Cloud                                                                                                         | 0.99          | 0.06       |
| Latin              | Viradouro                                                                                                                   | 0.99          | 0.06       |
| Rock               | Walking On The Water                                                                                                        | 0.99          | 0.06       |
| Rock               | Vertigo                                                                                                                     | 0.99          | 0.06       |
| Rock               | Someday Never Comes                                                                                                         | 0.99          | 0.06       |
| Rock               | It Ain't Like That                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Sister Awake                                                                                                                | 0.99          | 0.06       |
| Rock               | Night Flight                                                                                                                | 0.99          | 0.06       |
| Alternative & Punk | Radio Song                                                                                                                  | 0.99          | 0.06       |
| Rock               | Up Around The Bend                                                                                                          | 0.99          | 0.06       |
| Rock               | Over And Out                                                                                                                | 0.99          | 0.06       |
| Rock               | Nothingman                                                                                                                  | 0.99          | 0.06       |
| Latin              | Toda Menina Baiana                                                                                                          | 0.99          | 0.06       |
| Rock               | Dissident                                                                                                                   | 0.99          | 0.06       |
| Rock               | Breed                                                                                                                       | 0.99          | 0.06       |
| Rock               | Black Dog                                                                                                                   | 0.99          | 0.06       |
| Rock               | Sweet Soul Sister                                                                                                           | 0.99          | 0.06       |
| Rock               | Who Needs You                                                                                                               | 0.99          | 0.06       |
| Rock               | Who Wants To Live Forever                                                                                                   | 0.99          | 0.06       |
| Rock               | The First Time                                                                                                              | 0.99          | 0.06       |
| Metal              | Frantic                                                                                                                     | 0.99          | 0.06       |
| Latin              | O Último Romântico (Ao Vivo)                                                                                                | 0.99          | 0.06       |
| Latin              | Etnia                                                                                                                       | 0.99          | 0.06       |
| Rock               | Sanctuary                                                                                                                   | 0.99          | 0.06       |
| Rock               | The Crystal Ship                                                                                                            | 0.99          | 0.06       |
| Alternative & Punk | Release                                                                                                                     | 0.99          | 0.06       |
| Rock               | The Lemon Song                                                                                                              | 0.99          | 0.06       |
| Rock               | Ugly In The Morning                                                                                                         | 0.99          | 0.06       |
| Latin              | Coração Em Desalinho                                                                                                        | 0.99          | 0.06       |
| Latin              | Condição                                                                                                                    | 0.99          | 0.06       |
| Rock               | Animal                                                                                                                      | 0.99          | 0.06       |
| Rock               | Oceans                                                                                                                      | 0.99          | 0.06       |
| Latin              | Zambação                                                                                                                    | 0.99          | 0.06       |
| Rock               | Muçulmano                                                                                                                   | 0.99          | 0.06       |
| Metal              | Through The Never                                                                                                           | 0.99          | 0.06       |
| Latin              | Acelerou                                                                                                                    | 0.99          | 0.06       |
| Rock               | Don't Cry (Original)                                                                                                        | 0.99          | 0.06       |
| Rock               | Vavoom : Ted The Mechanic                                                                                                   | 0.99          | 0.06       |
| Latin              | Alô, Alô, Marciano                                                                                                          | 0.99          | 0.06       |
| Metal              | Crazy Train                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Maria                                                                                                                       | 0.99          | 0.06       |
| Rock               | Breathe                                                                                                                     | 0.99          | 0.06       |
| Latin              | Sincero Breu                                                                                                                | 0.99          | 0.06       |
| Rock               | 1/2 Full                                                                                                                    | 0.99          | 0.06       |
| Rock               | Maluco Beleza                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Green Grow The Rushes                                                                                                       | 0.99          | 0.06       |
| Rock               | Virginia Moon                                                                                                               | 0.99          | 0.06       |
| Metal              | You're Gonna Break My Hart Again                                                                                            | 0.99          | 0.06       |
| Alternative & Punk | Winterlong                                                                                                                  | 0.99          | 0.06       |
| Metal              | The Deeper The Love                                                                                                         | 0.99          | 0.06       |
| Latin              | Caleidoscópio                                                                                                               | 0.99          | 0.06       |
| Metal              | Changes                                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | Flores                                                                                                                      | 0.99          | 0.06       |
| Rock               | No Memory                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Kindergarten                                                                                                                | 0.99          | 0.06       |
| Latin              | Eu Amo Você                                                                                                                 | 0.99          | 0.06       |
| Rock               | Hysteria                                                                                                                    | 0.99          | 0.06       |
| Latin              | De Noite Na Cama                                                                                                            | 0.99          | 0.06       |
| Latin              | Santo Antonio                                                                                                               | 0.99          | 0.06       |
| Metal              | Holier Than Thou                                                                                                            | 0.99          | 0.06       |
| Latin              | Expresso 2222                                                                                                               | 0.99          | 0.06       |
| Latin              | Admirável Gado Novo                                                                                                         | 0.99          | 0.06       |
| Rock               | What It Takes                                                                                                               | 0.99          | 0.06       |
| Rock               | Little Guitars                                                                                                              | 0.99          | 0.06       |
| Latin              | O Que Me Importa                                                                                                            | 0.99          | 0.06       |
| Metal              | Seek & Destroy                                                                                                              | 0.99          | 0.06       |
| Metal              | Welcome Home (Sanitarium)                                                                                                   | 0.99          | 0.06       |
| Rock               | Love                                                                                                                        | 0.99          | 0.06       |
| Rock               | Satch Boogie                                                                                                                | 0.99          | 0.06       |
| Rock               | Love Child                                                                                                                  | 0.99          | 0.06       |
| Rock               | I Can See For Miles                                                                                                         | 0.99          | 0.06       |
| Rock               | Parallel Universe                                                                                                           | 0.99          | 0.06       |
| Rock               | Iron Man/Children of the Grave                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Top Top                                                                                                                     | 0.99          | 0.06       |
| Rock               | The Gentle Art Of Making Enemies                                                                                            | 0.99          | 0.06       |
| Rock               | On A Plain                                                                                                                  | 0.99          | 0.06       |
| Latin              | Eu Sou Neguinha (Ao Vivo)                                                                                                   | 0.99          | 0.06       |
| Rock               | I Could Die For You                                                                                                         | 0.99          | 0.06       |
| Latin              | Será Que Vai Chover?                                                                                                        | 0.99          | 0.06       |
| Metal              | The Trooper                                                                                                                 | 0.99          | 0.06       |
| Rock               | Headlong                                                                                                                    | 0.99          | 0.06       |
| Rock               | Hell Ain't A Bad Place To Be                                                                                                | 0.99          | 0.06       |
| Rock               | Thief In The Night                                                                                                          | 0.99          | 0.06       |
| Metal              | Some Kind Of Monster                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Losing My Religion                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Bankrobber                                                                                                                  | 0.99          | 0.06       |
| Latin              | Refazenda                                                                                                                   | 0.99          | 0.06       |
| Metal              | The Call Of Ktulu                                                                                                           | 0.99          | 0.06       |
| Metal              | Disposable Heroes                                                                                                           | 0.99          | 0.06       |
| Rock               | Friend Of A Friend                                                                                                          | 0.99          | 0.06       |
| Metal              | Children of the Damned                                                                                                      | 0.99          | 0.06       |
| Latin              | Atras Da Porta                                                                                                              | 0.99          | 0.06       |
| Latin              | Um Homem Chamado Alfredo                                                                                                    | 0.99          | 0.06       |
| Rock               | Pictures Of Lily                                                                                                            | 0.99          | 0.06       |
| Metal              | Freewheel Burning                                                                                                           | 0.99          | 0.06       |
| Rock               | The Show Must Go On                                                                                                         | 0.99          | 0.06       |
| Latin              | Música De Trabalho                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Shiny Happy People                                                                                                          | 0.99          | 0.06       |
| Rock               | When The Levee Breaks                                                                                                       | 0.99          | 0.06       |
| Latin              | Camarão que Dorme e Onda Leva                                                                                               | 0.99          | 0.06       |
| Rock               | Crumbs From Your Table                                                                                                      | 0.99          | 0.06       |
| Metal              | Super Terrorizer                                                                                                            | 0.99          | 0.06       |
| Rock               | Can't Stop Loving You                                                                                                       | 0.99          | 0.06       |
| Rock               | Celebration Day                                                                                                             | 0.99          | 0.06       |
| Metal              | Prowler                                                                                                                     | 0.99          | 0.06       |
| Rock               | Bleed The Freak                                                                                                             | 0.99          | 0.06       |
| Metal              | Master Of Puppets                                                                                                           | 0.99          | 0.06       |
| Latin              | Se...                                                                                                                       | 0.99          | 0.06       |
| Rock               | Moon Is Up                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Puteiro Em João Pessoa                                                                                                      | 0.99          | 0.06       |
| Rock               | Sleep On The Sidewalk                                                                                                       | 0.99          | 0.06       |
| Latin              | A Festa Do Santo Reis                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | Evil Dick                                                                                                                   | 0.99          | 0.06       |
| Rock               | Fear Is The Key                                                                                                             | 0.99          | 0.06       |
| Rock               | So Beautiful                                                                                                                | 0.99          | 0.06       |
| Latin              | Charles Anjo 45                                                                                                             | 0.99          | 0.06       |
| Rock               | Why Go                                                                                                                      | 0.99          | 0.06       |
| Metal              | Laguna Sunrise                                                                                                              | 0.99          | 0.06       |
| Rock               | Zé Trindade                                                                                                                 | 0.99          | 0.06       |
| Latin              | Samba pras moças                                                                                                            | 0.99          | 0.06       |
| Latin              | Fascinação                                                                                                                  | 0.99          | 0.06       |
| Rock               | Brain Damage                                                                                                                | 0.99          | 0.06       |
| Rock               | What Is And What Should Never Be                                                                                            | 0.99          | 0.06       |
| Rock               | Slave                                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | Texarkana                                                                                                                   | 0.99          | 0.06       |
| Rock               | All I Want Is You                                                                                                           | 0.99          | 0.06       |
| Rock               | Walk To The Water                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | My Mistake                                                                                                                  | 0.99          | 0.06       |
| Rock               | Can You See Me                                                                                                              | 0.99          | 0.06       |
| Rock               | Jesus Christ Pose                                                                                                           | 0.99          | 0.06       |
| Rock               | Hooked Up                                                                                                                   | 0.99          | 0.06       |
| Rock               | When The World Was Young                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Rhinocerous                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | A Sua                                                                                                                       | 0.99          | 0.06       |
| Metal              | Flying High Again                                                                                                           | 0.99          | 0.06       |
| Rock               | Lick It Up                                                                                                                  | 0.99          | 0.06       |
| Latin              | Um Satélite Na Cabeça                                                                                                       | 0.99          | 0.06       |
| Rock               | When Love Comes To Town                                                                                                     | 0.99          | 0.06       |
| Latin              | Do You Have Other Loves?                                                                                                    | 0.99          | 0.06       |
| Rock               | Black Night                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Polícia (Vinheta)                                                                                                           | 0.99          | 0.06       |
| Latin              | Mama Africa                                                                                                                 | 0.99          | 0.06       |
| Latin              | Dezesseis                                                                                                                   | 0.99          | 0.06       |
| Rock               | Going To California                                                                                                         | 0.99          | 0.06       |
| Rock               | Out On The Tiles                                                                                                            | 0.99          | 0.06       |
| Alternative & Punk | Are We The Waiting                                                                                                          | 0.99          | 0.06       |
| Rock               | On Fire                                                                                                                     | 0.99          | 0.06       |
| Rock               | El Farol                                                                                                                    | 0.99          | 0.06       |
| Rock               | Spirit Walker                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Rollover D.J.                                                                                                               | 0.99          | 0.06       |
| Latin              | La Bella Luna                                                                                                               | 0.99          | 0.06       |
| Rock               | Fly By Night                                                                                                                | 0.99          | 0.06       |
| Latin              | Sereia                                                                                                                      | 0.99          | 0.06       |
| Rock               | Lightning Strikes Twice                                                                                                     | 0.99          | 0.06       |
| Rock               | Prowler                                                                                                                     | 0.99          | 0.06       |
| Rock               | Even Better Than The Real Thing                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | Sir Psycho Sexy                                                                                                             | 0.99          | 0.06       |
| Latin              | Realce                                                                                                                      | 0.99          | 0.06       |
| Latin              | Samba Pra Endrigo                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Bê-a-Bá                                                                                                                     | 0.99          | 0.06       |
| Metal              | Home Sweet Home                                                                                                             | 0.99          | 0.06       |
| Rock               | Too Young To Die                                                                                                            | 0.99          | 0.06       |
| Rock               | Friends                                                                                                                     | 0.99          | 0.06       |
| Metal              | Jerusalem                                                                                                                   | 0.99          | 0.06       |
| Metal              | Slither                                                                                                                     | 0.99          | 0.06       |
| Rock               | When Love & Hate Collide                                                                                                    | 0.99          | 0.06       |
| Rock               | Pinball Wizard                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | [Untitled]                                                                                                                  | 0.99          | 0.06       |
| Rock               | Creep                                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | The Power Of Equality                                                                                                       | 0.99          | 0.06       |
| Latin              | Brasília 5:31                                                                                                               | 0.99          | 0.06       |
| Metal              | The Memory Remains                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Hairshirt                                                                                                                   | 0.99          | 0.06       |
| Rock               | Os Exilados                                                                                                                 | 0.99          | 0.06       |
| Rock               | Midnight                                                                                                                    | 0.99          | 0.06       |
| Rock               | F*Ckin' Up                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Jesus Of Suburbia / City Of The Damned / I Don't Care / Dearly Beloved / Tales Of Another Broken Home                       | 0.99          | 0.06       |
| Latin              | Dujji                                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | KKK Bitch                                                                                                                   | 0.99          | 0.06       |
| Rock               | Love And Peace Or Else                                                                                                      | 0.99          | 0.06       |
| Alternative & Punk | Are You Gonna Be My Girl                                                                                                    | 0.99          | 0.06       |
| Latin              | O Que Será (À Flor Da Terra)                                                                                                | 0.99          | 0.06       |
| Metal              | The Outlaw Torn                                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | Your Time Has Come                                                                                                          | 0.99          | 0.06       |
| Latin              | Vamo Batê Lata                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Querem Meu Sangue                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Marvin                                                                                                                      | 0.99          | 0.06       |
| Rock               | Boogie With Stu                                                                                                             | 0.99          | 0.06       |
| Metal              | Creeping Death                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Got That Feeling                                                                                                            | 0.99          | 0.06       |
| Rock               | Back Door Man                                                                                                               | 0.99          | 0.06       |
| Rock               | Unchained                                                                                                                   | 0.99          | 0.06       |
| Rock               | Your Time Is Gonna Come                                                                                                     | 0.99          | 0.06       |
| Metal              | Prince Charming                                                                                                             | 0.99          | 0.06       |
| Latin              | Dança Da Solidão                                                                                                            | 0.99          | 0.06       |
| Latin              | Mas Que Nada                                                                                                                | 0.99          | 0.06       |
| Latin              | Socorro                                                                                                                     | 0.99          | 0.06       |
| Rock               | Get On The Snake                                                                                                            | 0.99          | 0.06       |
| Latin              | União Da Ilha                                                                                                               | 0.99          | 0.06       |
| Latin              | Samba Makossa                                                                                                               | 0.99          | 0.06       |
| Latin              | Maracatu Atômico                                                                                                            | 0.99          | 0.06       |
| Latin              | Prenda Minha                                                                                                                | 0.99          | 0.06       |
| Rock               | Bad Moon Rising                                                                                                             | 0.99          | 0.06       |
| Metal              | Yesterdays                                                                                                                  | 0.99          | 0.06       |
| Rock               | Primavera                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Dandelion                                                                                                                   | 0.99          | 0.06       |
| Rock               | Women In Uniform                                                                                                            | 0.99          | 0.06       |
| Rock               | Childhoods End?                                                                                                             | 0.99          | 0.06       |
| Rock               | Dust N' Bones                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Rita Lee                                                                                                                    | 0.99          | 0.06       |
| Rock               | Carolina Hard-Core Ecstasy                                                                                                  | 0.99          | 0.06       |
| Rock               | No More Tears                                                                                                               | 0.99          | 0.06       |
| Rock               | Green River                                                                                                                 | 0.99          | 0.06       |
| Rock               | Original Of The Species                                                                                                     | 0.99          | 0.06       |
| Rock               | Bohemian Rhapsody                                                                                                           | 0.99          | 0.06       |
| Rock               | With Or Without You                                                                                                         | 0.99          | 0.06       |
| Rock               | Lil' Evil                                                                                                                   | 0.99          | 0.06       |
| Rock               | Fortunes Of War                                                                                                             | 0.99          | 0.06       |
| Metal              | Primal Scream                                                                                                               | 0.99          | 0.06       |
| Latin              | A Paz                                                                                                                       | 0.99          | 0.06       |
| Latin              | Entre E Ouça                                                                                                                | 0.99          | 0.06       |
| Rock               | Poeira                                                                                                                      | 0.99          | 0.06       |
| Metal              | Radio/Video                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Helpless                                                                                                                    | 0.99          | 0.06       |
| Rock               | Respectable                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Naked In The Rain                                                                                                           | 0.99          | 0.06       |
| Latin              | Um Passeio No Mundo Livre                                                                                                   | 0.99          | 0.06       |
| Latin              | Sítio Do Pica-Pau Amarelo                                                                                                   | 0.99          | 0.06       |
| Metal              | Heart Of Gold                                                                                                               | 0.99          | 0.06       |
| Latin              | O Trem Da Juventude                                                                                                         | 0.99          | 0.06       |
| Rock               | Like a Stone                                                                                                                | 0.99          | 0.06       |
| Latin              | Livre Pra Viver                                                                                                             | 0.99          | 0.06       |
| Rock               | Stone Free                                                                                                                  | 0.99          | 0.06       |
| Latin              | Sangue De Bairro                                                                                                            | 0.99          | 0.06       |
| Rock               | Black Light Syndrome                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Midnight Cowboy                                                                                                             | 0.99          | 0.06       |
| Rock               | Still                                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | Homem Primata                                                                                                               | 0.99          | 0.06       |
| Metal              | Cigaro                                                                                                                      | 0.99          | 0.06       |
| Rock               | Humans Being                                                                                                                | 0.99          | 0.06       |
| Rock               | Maquinarama                                                                                                                 | 0.99          | 0.06       |
| Metal              | The Tower                                                                                                                   | 0.99          | 0.06       |
| Latin              | Sozinho (Caêdrum 'n' Bass)                                                                                                  | 0.99          | 0.06       |
| Rock               | Love Don't Mean a Thing                                                                                                     | 0.99          | 0.06       |
| Rock               | It's Just A Thought                                                                                                         | 0.99          | 0.06       |
| Metal              | Gates Of Urizen                                                                                                             | 0.99          | 0.06       |
| Rock               | O Braço Da Minha Guitarra                                                                                                   | 0.99          | 0.06       |
| Rock               | That's The Way                                                                                                              | 0.99          | 0.06       |
| Rock               | Still Loving You                                                                                                            | 0.99          | 0.06       |
| Rock               | The Battle Rages On                                                                                                         | 0.99          | 0.06       |
| Rock               | Spread Your Wings                                                                                                           | 0.99          | 0.06       |
| Metal              | Am I Evil?                                                                                                                  | 0.99          | 0.06       |
| Rock               | Drowning Man                                                                                                                | 0.99          | 0.06       |
| Latin              | Satisfação                                                                                                                  | 0.99          | 0.06       |
| Rock               | Blood On The World's Hands                                                                                                  | 0.99          | 0.06       |
| Metal              | Heaven Can Wait                                                                                                             | 0.99          | 0.06       |
| Rock               | Child In Time                                                                                                               | 0.99          | 0.06       |
| Latin              | Busca Vida                                                                                                                  | 0.99          | 0.06       |
| Metal              | Live To Win                                                                                                                 | 0.99          | 0.06       |
| Latin              | Réu Confesso                                                                                                                | 0.99          | 0.06       |
| Rock               | Take This Bottle                                                                                                            | 0.99          | 0.06       |
| Rock               | Space Truckin'                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Stripsearch                                                                                                                 | 0.99          | 0.06       |
| Rock               | All Because Of You                                                                                                          | 0.99          | 0.06       |
| Rock               | It's So Easy                                                                                                                | 0.99          | 0.06       |
| Rock               | King Of Dreams                                                                                                              | 0.99          | 0.06       |
| Latin              | Quanta (Live)                                                                                                               | 0.99          | 0.06       |
| Rock               | Fall To Pieces                                                                                                              | 0.99          | 0.06       |
| Rock               | As Tears Go By                                                                                                              | 0.99          | 0.06       |
| Metal              | Damage Inc.                                                                                                                 | 0.99          | 0.06       |
| Rock               | All I Really Want                                                                                                           | 0.99          | 0.06       |
| Rock               | Blue Train                                                                                                                  | 0.99          | 0.06       |
| Metal              | Brave New World                                                                                                             | 0.99          | 0.06       |
| Rock               | Set It Off                                                                                                                  | 0.99          | 0.06       |
| Rock               | The Fly                                                                                                                     | 0.99          | 0.06       |
| Rock               | Futureal                                                                                                                    | 0.99          | 0.06       |
| Rock               | Fast As a Shark                                                                                                             | 0.99          | 0.06       |
| Latin              | Tatuagem                                                                                                                    | 0.99          | 0.06       |
| Metal              | Jailbait                                                                                                                    | 0.99          | 0.06       |
| Metal              | Invisible Kid                                                                                                               | 0.99          | 0.06       |
| Rock               | For Those About To Rock (We Salute You)                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | The River (Remix)                                                                                                           | 0.99          | 0.06       |
| Rock               | Around The World                                                                                                            | 0.99          | 0.06       |
| Metal              | Wasting Love                                                                                                                | 0.99          | 0.06       |
| Alternative & Punk | Overdrive                                                                                                                   | 0.99          | 0.06       |
| Rock               | Tea For One                                                                                                                 | 0.99          | 0.06       |
| Rock               | Moby Dick                                                                                                                   | 0.99          | 0.06       |
| Latin              | Nem Um Dia                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Everything's Ruined                                                                                                         | 0.99          | 0.06       |
| Metal              | Metal Militia                                                                                                               | 0.99          | 0.06       |
| Rock               | Love Is Blindness                                                                                                           | 0.99          | 0.06       |
| Metal              | Civil War                                                                                                                   | 0.99          | 0.06       |
| Latin              | Apesar De Você                                                                                                              | 0.99          | 0.06       |
| Rock               | We're Gonna Groove                                                                                                          | 0.99          | 0.06       |
| Rock               | Três Lados                                                                                                                  | 0.99          | 0.06       |
| Latin              | Opachorô (Live)                                                                                                             | 0.99          | 0.06       |
| Rock               | Thank You                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Smoked Pork                                                                                                                 | 0.99          | 0.06       |
| Rock               | Bicycle Race                                                                                                                | 0.99          | 0.06       |
| Metal              | The More I See                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Longview                                                                                                                    | 0.99          | 0.06       |
| Latin              | Soul Parsifal                                                                                                               | 0.99          | 0.06       |
| Rock               | Whole Lotta Love                                                                                                            | 0.99          | 0.06       |
| Latin              | Beijo Partido                                                                                                               | 0.99          | 0.06       |
| Metal              | Where The Wild Things Are                                                                                                   | 0.99          | 0.06       |
| Rock               | Real Thing                                                                                                                  | 0.99          | 0.06       |
| Rock               | Fortunate Son                                                                                                               | 0.99          | 0.06       |
| Rock               | Road Trippin'                                                                                                               | 0.99          | 0.06       |
| Latin              | Onibusfobia                                                                                                                 | 0.99          | 0.06       |
| Metal              | Of Wolf And Man                                                                                                             | 0.99          | 0.06       |
| Latin              | Vai Passar                                                                                                                  | 0.99          | 0.06       |
| Rock               | Spellbound                                                                                                                  | 0.99          | 0.06       |
| Rock               | Fire                                                                                                                        | 0.99          | 0.06       |
| Rock               | Zither                                                                                                                      | 0.99          | 0.06       |
| Rock               | Animal                                                                                                                      | 0.99          | 0.06       |
| Rock               | Tease Me Please Me                                                                                                          | 0.99          | 0.06       |
| Rock               | The Sun Road                                                                                                                | 0.99          | 0.06       |
| Rock               | Quem Mata A Mulher Mata O Melhor                                                                                            | 0.99          | 0.06       |
| Rock               | Bleed Together                                                                                                              | 0.99          | 0.06       |
| Metal              | Losfer Words                                                                                                                | 0.99          | 0.06       |
| Rock               | King For A Day                                                                                                              | 0.99          | 0.06       |
| Metal              | Tuesday's Gone                                                                                                              | 0.99          | 0.06       |
| Rock               | Highway Chile                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Body Count's In The House                                                                                                   | 0.99          | 0.06       |
| Rock               | Às Vezes                                                                                                                    | 0.99          | 0.06       |
| Latin              | Oceano                                                                                                                      | 0.99          | 0.06       |
| Rock               | Trash, Trampoline And The Party Girl                                                                                        | 0.99          | 0.06       |
| Latin              | Odara                                                                                                                       | 0.99          | 0.06       |
| Latin              | Para Lennon E McCartney                                                                                                     | 0.99          | 0.06       |
| Latin              | Tempo Rei                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Surprise! You're Dead!                                                                                                      | 0.99          | 0.06       |
| Rock               | Into The Light                                                                                                              | 0.99          | 0.06       |
| Rock               | That's The Way                                                                                                              | 0.99          | 0.06       |
| Rock               | Black Mountain Side                                                                                                         | 0.99          | 0.06       |
| Latin              | A Noite Do Meu Bem                                                                                                          | 0.99          | 0.06       |
| Latin              | Gostava Tanto De Você                                                                                                       | 0.99          | 0.06       |
| Latin              | Divirta-Se (Saindo Da Sua)                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Extraordinary Girl                                                                                                          | 0.99          | 0.06       |
| Metal              | Flash of The Blade                                                                                                          | 0.99          | 0.06       |
| Metal              | Sign Of The Cross                                                                                                           | 0.99          | 0.06       |
| Metal              | Still Life                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Stand Inside Your Love                                                                                                      | 0.99          | 0.06       |
| Latin              | Navegar Impreciso                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Palavras                                                                                                                    | 0.99          | 0.06       |
| Rock               | 5.15                                                                                                                        | 0.99          | 0.06       |
| Metal              | Holy Smoke                                                                                                                  | 0.99          | 0.06       |
| Metal              | Please Don't Touch                                                                                                          | 0.99          | 0.06       |
| Rock               | Out Of Tears                                                                                                                | 0.99          | 0.06       |
| Latin              | Denúncia                                                                                                                    | 0.99          | 0.06       |
| Latin              | Reggae Odoyá                                                                                                                | 0.99          | 0.06       |
| Metal              | Jump In The Fire                                                                                                            | 0.99          | 0.06       |
| Latin              | Felicidade Urgente                                                                                                          | 0.99          | 0.06       |
| Latin              | Trac Trac                                                                                                                   | 0.99          | 0.06       |
| Rock               | Exploder                                                                                                                    | 0.99          | 0.06       |
| Metal              | Hit The Lights                                                                                                              | 0.99          | 0.06       |
| Rock               | Hypnotize                                                                                                                   | 0.99          | 0.06       |
| Metal              | Run to the Hills                                                                                                            | 0.99          | 0.06       |
| Rock               | Porch                                                                                                                       | 0.99          | 0.06       |
| Rock               | The Educated Fool                                                                                                           | 0.99          | 0.06       |
| Latin              | Você Fugiu                                                                                                                  | 0.99          | 0.06       |
| Latin              | Romaria (Renato Teixeira)                                                                                                   | 0.99          | 0.06       |
| Latin              | Aprendendo A Jogar                                                                                                          | 0.99          | 0.06       |
| Metal              | Caught Somewhere in Time                                                                                                    | 0.99          | 0.06       |
| Rock               | Can't Stand Losing You                                                                                                      | 0.99          | 0.06       |
| Metal              | I Fucking Hate You                                                                                                          | 0.99          | 0.06       |
| Rock               | Duende                                                                                                                      | 0.99          | 0.06       |
| Metal              | Heaven Can Wait                                                                                                             | 0.99          | 0.06       |
| Rock               | King Of Pain                                                                                                                | 0.99          | 0.06       |
| Rock               | Squeeze Box                                                                                                                 | 0.99          | 0.06       |
| Rock               | It's Only Love                                                                                                              | 0.99          | 0.06       |
| Rock               | Immigrant Song                                                                                                              | 0.99          | 0.06       |
| Latin              | Flor De Lis                                                                                                                 | 0.99          | 0.06       |
| Latin              | All Star                                                                                                                    | 0.99          | 0.06       |
| Rock               | Dancing In The Street                                                                                                       | 0.99          | 0.06       |
| Rock               | Elza                                                                                                                        | 0.99          | 0.06       |
| Latin              | Brasil                                                                                                                      | 0.99          | 0.06       |
| Metal              | Harvester Of Sorrow                                                                                                         | 0.99          | 0.06       |
| Rock               | Two Steps Behind [Acoustic Version]                                                                                         | 0.99          | 0.06       |
| Rock               | Love Gun                                                                                                                    | 0.99          | 0.06       |
| Rock               | Dog Eat Dog                                                                                                                 | 0.99          | 0.06       |
| Latin              | As Aparências Enganam                                                                                                       | 0.99          | 0.06       |
| Latin              | Banditismo Por Uma Questa                                                                                                   | 0.99          | 0.06       |
| Rock               | I Can't Remember                                                                                                            | 0.99          | 0.06       |
| Rock               | Feel Your Love Tonight                                                                                                      | 0.99          | 0.06       |
| Rock               | Like A Song...                                                                                                              | 0.99          | 0.06       |
| Rock               | Cry For Love                                                                                                                | 0.99          | 0.06       |
| Alternative & Punk | Army Ants                                                                                                                   | 0.99          | 0.06       |
| Rock               | Save Me                                                                                                                     | 0.99          | 0.06       |
| Latin              | Dance Enquanto é Tempo                                                                                                      | 0.99          | 0.06       |
| Latin              | Atrás da Porta                                                                                                              | 0.99          | 0.06       |
| Rock               | Ten Years Gone                                                                                                              | 0.99          | 0.06       |
| Rock               | Bittersweet Me                                                                                                              | 0.99          | 0.06       |
| Metal              | The Trooper                                                                                                                 | 0.99          | 0.06       |
| Rock               | Run Through The Jungle                                                                                                      | 0.99          | 0.06       |
| Rock               | Thank You                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Psychopomp                                                                                                                  | 0.99          | 0.06       |
| Latin              | A Banda                                                                                                                     | 0.99          | 0.06       |
| Rock               | Rock And Roll Is Dead                                                                                                       | 0.99          | 0.06       |
| Rock               | When Love Comes To Town                                                                                                     | 0.99          | 0.06       |
| Rock               | Princess of the Dawn                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Homecoming / The Death Of St. Jimmy / East 12th St. / Nobody Likes You / Rock And Roll Girlfriend / We're Coming Home Again | 0.99          | 0.06       |
| Alternative & Punk | Woodpecker From Mars                                                                                                        | 0.99          | 0.06       |
| Rock               | In Bloom                                                                                                                    | 0.99          | 0.06       |
| Latin              | So Por Amor                                                                                                                 | 0.99          | 0.06       |
| Rock               | Acrobat                                                                                                                     | 0.99          | 0.06       |
| Rock               | Chains Of Misery                                                                                                            | 0.99          | 0.06       |
| Rock               | Iron Maiden                                                                                                                 | 0.99          | 0.06       |
| Rock               | Out Ta Get Me                                                                                                               | 0.99          | 0.06       |
| Rock               | Paint It Black                                                                                                              | 0.99          | 0.06       |
| Rock               | Monkey Wrench                                                                                                               | 0.99          | 0.06       |
| Latin              | Idolatrada                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Macy's Day Parade                                                                                                           | 0.99          | 0.06       |
| Latin              | Desaforo                                                                                                                    | 0.99          | 0.06       |
| Rock               | Can't Keep                                                                                                                  | 0.99          | 0.06       |
| Latin              | Formigueiro                                                                                                                 | 0.99          | 0.06       |
| Rock               | Every Breath You Take                                                                                                       | 0.99          | 0.06       |
| Latin              | Maria Fumaça                                                                                                                | 0.99          | 0.06       |
| Metal              | Kickstart My Heart                                                                                                          | 0.99          | 0.06       |
| Latin              | Vida Boa                                                                                                                    | 0.99          | 0.06       |
| Rock               | 2 A.M.                                                                                                                      | 0.99          | 0.06       |
| Rock               | Been A Son                                                                                                                  | 0.99          | 0.06       |
| Latin              | Vai Valer                                                                                                                   | 0.99          | 0.06       |
| Rock               | Waterhole (Expresso Bongo)                                                                                                  | 0.99          | 0.06       |
| Rock               | Como Estais Amigos                                                                                                          | 0.99          | 0.06       |
| Metal              | Powerslave                                                                                                                  | 0.99          | 0.06       |
| Rock               | Blood Brothers                                                                                                              | 0.99          | 0.06       |
| Rock               | What If I Do?                                                                                                               | 0.99          | 0.06       |
| Latin              | Ro-Que-Se-Da-Ne                                                                                                             | 0.99          | 0.06       |
| Rock               | Night Time Is The Right Time                                                                                                | 0.99          | 0.06       |
| Rock               | Crackerman                                                                                                                  | 0.99          | 0.06       |
| Rock               | Heartland                                                                                                                   | 0.99          | 0.06       |
| Rock               | Fear Of The Dark                                                                                                            | 0.99          | 0.06       |
| Rock               | Every Time I Look At You                                                                                                    | 0.99          | 0.06       |
| Rock               | Desire                                                                                                                      | 0.99          | 0.06       |
| Alternative & Punk | Body Count                                                                                                                  | 0.99          | 0.06       |
| Latin              | SKA                                                                                                                         | 0.99          | 0.06       |
| Latin              | Tudo Na Mais Santa Paz                                                                                                      | 0.99          | 0.06       |
| Latin              | Wave (Os Cariocas)                                                                                                          | 0.99          | 0.06       |
| Rock               | When You Gonna Learn (Digeridoo)                                                                                            | 0.99          | 0.06       |
| Metal              | Turn The Page                                                                                                               | 0.99          | 0.06       |
| Latin              | Sozinho                                                                                                                     | 0.99          | 0.06       |
| Rock               | My Melancholy Blues                                                                                                         | 0.99          | 0.06       |
| Metal              | Iron Maiden                                                                                                                 | 0.99          | 0.06       |
| Rock               | In Your Honor                                                                                                               | 0.99          | 0.06       |
| Rock               | Surrender                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Tommy Gun                                                                                                                   | 0.99          | 0.06       |
| Rock               | I Can't Explain                                                                                                             | 0.99          | 0.06       |
| Rock               | Sheer Heart Attack                                                                                                          | 0.99          | 0.06       |
| Rock               | La Puesta Del Sol                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Eu E Ela                                                                                                                    | 0.99          | 0.06       |
| Rock               | Under Pressure                                                                                                              | 0.99          | 0.06       |
| Rock               | Stars                                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | Redundant                                                                                                                   | 0.99          | 0.06       |
| Rock               | Porcelain                                                                                                                   | 0.99          | 0.06       |
| Metal              | The Prophecy                                                                                                                | 0.99          | 0.06       |
| Latin              | Os Alquimistas Estão Chegando                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Yesterday To Tomorrow                                                                                                       | 0.99          | 0.06       |
| Rock               | Flight Of The Rat                                                                                                           | 0.99          | 0.06       |
| Metal              | Transylvania                                                                                                                | 0.99          | 0.06       |
| Latin              | Você Passa, Eu Acho Graça (Ao Vivo)                                                                                         | 0.99          | 0.06       |
| Latin              | O Leaozinho                                                                                                                 | 0.99          | 0.06       |
| Rock               | Século XXI                                                                                                                  | 0.99          | 0.06       |
| Rock               | Love In An Elevator                                                                                                         | 0.99          | 0.06       |
| Rock               | The Right Thing                                                                                                             | 0.99          | 0.06       |
| Rock               | I Still Love You                                                                                                            | 0.99          | 0.06       |
| Latin              | Meu Mundo Fica Completo (Com Você)                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Radio Free Aurope                                                                                                           | 0.99          | 0.06       |
| Metal              | Metal Meltdown                                                                                                              | 0.99          | 0.06       |
| Rock               | Confusion                                                                                                                   | 0.99          | 0.06       |
| Latin              | Um Love                                                                                                                     | 0.99          | 0.06       |
| Rock               | Wet My Bed                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | She                                                                                                                         | 0.99          | 0.06       |
| Rock               | Panama                                                                                                                      | 0.99          | 0.06       |
| Alternative & Punk | Go Back                                                                                                                     | 0.99          | 0.06       |
| Rock               | Anthem                                                                                                                      | 0.99          | 0.06       |
| Metal              | Relvelation (Mother Earth)                                                                                                  | 0.99          | 0.06       |
| Rock               | A Touch Away                                                                                                                | 0.99          | 0.06       |
| Latin              | Estrela (Live)                                                                                                              | 0.99          | 0.06       |
| Rock               | Sanctuary                                                                                                                   | 0.99          | 0.06       |
| Metal              | All For You                                                                                                                 | 0.99          | 0.06       |
| Latin              | O Descobridor Dos Sete Mares                                                                                                | 0.99          | 0.06       |
| Latin              | O Xote Das Meninas                                                                                                          | 0.99          | 0.06       |
| Latin              | Balanço                                                                                                                     | 0.99          | 0.06       |
| Metal              | Bring Your Daughter... To The Slaughter                                                                                     | 0.99          | 0.06       |
| Latin              | Cigano                                                                                                                      | 0.99          | 0.06       |
| Rock               | Desire                                                                                                                      | 0.99          | 0.06       |
| Rock               | Bad Obsession                                                                                                               | 0.99          | 0.06       |
| Rock               | Sick Again                                                                                                                  | 0.99          | 0.06       |
| Rock               | Nothin' To Lose                                                                                                             | 0.99          | 0.06       |
| Rock               | Molina                                                                                                                      | 0.99          | 0.06       |
| Rock               | Evil Ways                                                                                                                   | 0.99          | 0.06       |
| Rock               | The Fugitive                                                                                                                | 0.99          | 0.06       |
| Latin              | Coroné Antonio Bento                                                                                                        | 0.99          | 0.06       |
| Metal              | Eye Of The Beholder                                                                                                         | 0.99          | 0.06       |
| Rock               | Restless and Wild                                                                                                           | 0.99          | 0.06       |
| Rock               | American Woman                                                                                                              | 0.99          | 0.06       |
| Rock               | Misty Mountain Hop                                                                                                          | 0.99          | 0.06       |
| Rock               | I Want It All                                                                                                               | 0.99          | 0.06       |
| Latin              | Construção / Deus Lhe Pague                                                                                                 | 0.99          | 0.06       |
| Rock               | Man On The Edge                                                                                                             | 0.99          | 0.06       |
| Latin              | Meninos E Meninas                                                                                                           | 0.99          | 0.06       |
| Rock               | Pseudo Silk Kimono                                                                                                          | 0.99          | 0.06       |
| Rock               | Nothing To Say                                                                                                              | 0.99          | 0.06       |
| Metal              | Sea of Madness                                                                                                              | 0.99          | 0.06       |
| Metal              | Make Me Believe                                                                                                             | 0.99          | 0.06       |
| Metal              | Straight Out Of Line                                                                                                        | 0.99          | 0.06       |
| Rock               | Cuckoo For Caca                                                                                                             | 0.99          | 0.06       |
| Latin              | Only A Dream In Rio                                                                                                         | 0.99          | 0.06       |
| Latin              | Banditismo Por Uma Questa                                                                                                   | 0.99          | 0.06       |
| Latin              | Palavras Ao Vento                                                                                                           | 0.99          | 0.06       |
| Rock               | Big Machine                                                                                                                 | 0.99          | 0.06       |
| Rock               | Think About You                                                                                                             | 0.99          | 0.06       |
| Latin              | Parabolicamará                                                                                                              | 0.99          | 0.06       |
| Rock               | Love Of My Life                                                                                                             | 0.99          | 0.06       |
| Metal              | Realword                                                                                                                    | 0.99          | 0.06       |
| Rock               | Ain't Talkin' 'bout Love                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Rock On                                                                                                                     | 0.99          | 0.06       |
| Latin              | Aquilo                                                                                                                      | 0.99          | 0.06       |
| Rock               | Off He Goes                                                                                                                 | 0.99          | 0.06       |
| Latin              | Caprichosos                                                                                                                 | 0.99          | 0.06       |
| Rock               | Comin' Home                                                                                                                 | 0.99          | 0.06       |
| Rock               | Suck On The Jugular                                                                                                         | 0.99          | 0.06       |
| Rock               | Wild Hearted Son                                                                                                            | 0.99          | 0.06       |
| Metal              | Diamonds And Rust (Live)                                                                                                    | 0.99          | 0.06       |
| Metal              | To Live Is To Die                                                                                                           | 0.99          | 0.06       |
| Rock               | Garota Nacional                                                                                                             | 0.99          | 0.06       |
| Rock               | A Twist In The Tail                                                                                                         | 0.99          | 0.06       |
| Latin              | Cristina Nº 2                                                                                                               | 0.99          | 0.06       |
| Rock               | Alive                                                                                                                       | 0.99          | 0.06       |
| Rock               | The Unbeliever                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Mouth To Mouth                                                                                                              | 0.99          | 0.06       |
| Metal              | Looking For Love                                                                                                            | 0.99          | 0.06       |
| Latin              | Padre Cícero                                                                                                                | 0.99          | 0.06       |
| Rock               | Hots On For Nowhere                                                                                                         | 0.99          | 0.06       |
| Rock               | The Seeker                                                                                                                  | 0.99          | 0.06       |
| Latin              | Linha Do Horizonte                                                                                                          | 0.99          | 0.06       |
| Latin              | Selvagem                                                                                                                    | 0.99          | 0.06       |
| Rock               | Pour Some Sugar On Me                                                                                                       | 0.99          | 0.06       |
| Latin              | Eleanor Rigby                                                                                                               | 0.99          | 0.06       |
| Latin              | Assaltaram A Gramática                                                                                                      | 0.99          | 0.06       |
| Rock               | The Ocean                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | World Wide Suicide                                                                                                          | 0.99          | 0.06       |
| Latin              | Atrás Da Verd-E-Rosa Só Não Vai Quem Já Morreu                                                                              | 0.99          | 0.06       |
| Rock               | Livin' On The Edge                                                                                                          | 0.99          | 0.06       |
| Rock               | Janie's Got A Gun                                                                                                           | 0.99          | 0.06       |
| Rock               | This Is The Place                                                                                                           | 0.99          | 0.06       |
| Rock               | Nico                                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Vida De Cachorro                                                                                                            | 0.99          | 0.06       |
| Latin              | Computadores Fazem Arte                                                                                                     | 0.99          | 0.06       |
| Alternative & Punk | You Are The Everything                                                                                                      | 0.99          | 0.06       |
| Rock               | Heartbreaker                                                                                                                | 0.99          | 0.06       |
| Rock               | The Angel And The Gambler                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Meu Refrigerador Não Funciona                                                                                               | 0.99          | 0.06       |
| Rock               | The Zoo                                                                                                                     | 0.99          | 0.06       |
| Latin              | Não Dá Mais Pra Segurar (Explode Coração)                                                                                   | 0.99          | 0.06       |
| Latin              | Você                                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Underwater Love                                                                                                             | 0.99          | 0.06       |
| Rock               | Brighter Than a Thousand Suns                                                                                               | 0.99          | 0.06       |
| Latin              | Dezesseis                                                                                                                   | 0.99          | 0.06       |
| Latin              | Acelerou                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Caras Como Eu                                                                                                               | 0.99          | 0.06       |
| Rock               | War (The Process)                                                                                                           | 0.99          | 0.06       |
| Metal              | Where Eagles Dare                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | Burn Away                                                                                                                   | 0.99          | 0.06       |
| Rock               | Sanctuary                                                                                                                   | 0.99          | 0.06       |
| Rock               | So Cruel                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Os Cegos Do Castelo                                                                                                         | 0.99          | 0.06       |
| Rock               | I Want To Break Free                                                                                                        | 0.99          | 0.06       |
| Metal              | Bleeding Me                                                                                                                 | 0.99          | 0.06       |
| Rock               | Leave                                                                                                                       | 0.99          | 0.06       |
| Rock               | Rock & Roll                                                                                                                 | 0.99          | 0.06       |
| Rock               | Bark at the Moon                                                                                                            | 0.99          | 0.06       |
| Rock               | Red House                                                                                                                   | 0.99          | 0.06       |
| Rock               | She                                                                                                                         | 0.99          | 0.06       |
| Latin              | Será                                                                                                                        | 0.99          | 0.06       |
| Rock               | Santana Jam                                                                                                                 | 0.99          | 0.06       |
| Rock               | Back off Bitch                                                                                                              | 0.99          | 0.06       |
| Rock               | Sympton of the Universe                                                                                                     | 0.99          | 0.06       |
| Metal              | The Begining... At Last                                                                                                     | 0.99          | 0.06       |
| Latin              | O Beco                                                                                                                      | 0.99          | 0.06       |
| Rock               | I Can't Explain                                                                                                             | 0.99          | 0.06       |
| Alternative & Punk | Não Vou Lutar                                                                                                               | 0.99          | 0.06       |
| Rock               | You Really Got Me                                                                                                           | 0.99          | 0.06       |
| Rock               | Lord Of The Flies                                                                                                           | 0.99          | 0.06       |
| Rock               | Dream Of Mirrors                                                                                                            | 0.99          | 0.06       |
| Rock               | The Pilgrim                                                                                                                 | 0.99          | 0.06       |
| Latin              | Ponto De Interrogação                                                                                                       | 0.99          | 0.06       |
| Rock               | True Believers                                                                                                              | 0.99          | 0.06       |
| Metal              | Whiplash                                                                                                                    | 0.99          | 0.06       |
| Rock               | I Know Somethin (Bout You)                                                                                                  | 0.99          | 0.06       |
| Rock               | Communication Breakdown(2)                                                                                                  | 0.99          | 0.06       |
| Rock               | Dancing Barefoot                                                                                                            | 0.99          | 0.06       |
| Latin              | Um Amor Puro                                                                                                                | 0.99          | 0.06       |
| Alternative & Punk | Mellowship Slinky In B Major                                                                                                | 0.99          | 0.06       |
| Rock               | Closer To The Heart                                                                                                         | 0.99          | 0.06       |
| Metal              | Revenga                                                                                                                     | 0.99          | 0.06       |
| Metal              | Bad Seed                                                                                                                    | 0.99          | 0.06       |
| Metal              | Helpless                                                                                                                    | 0.99          | 0.06       |
| Rock               | Do You Feel Loved                                                                                                           | 0.99          | 0.06       |
| Rock               | Gimmie Shelters                                                                                                             | 0.99          | 0.06       |
| Rock               | Breakthru                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | The Finest Worksong                                                                                                         | 0.99          | 0.06       |
| Rock               | Stormbringer                                                                                                                | 0.99          | 0.06       |
| Metal              | Fuel                                                                                                                        | 0.99          | 0.06       |
| Rock               | From Here To Eternity                                                                                                       | 0.99          | 0.06       |
| Latin              | Metrô. Linha 743                                                                                                            | 0.99          | 0.06       |
| Latin              | Vôo Sobre o Horizonte                                                                                                       | 0.99          | 0.06       |
| Latin              | Cérebro Eletrônico                                                                                                          | 0.99          | 0.06       |
| Rock               | Anyway, Anyhow, Anywhere                                                                                                    | 0.99          | 0.06       |
| Rock               | Can't Stop                                                                                                                  | 0.99          | 0.06       |
| Metal              | Die Die My Darling                                                                                                          | 0.99          | 0.06       |
| Rock               | Believe                                                                                                                     | 0.99          | 0.06       |
| Rock               | Loud Love                                                                                                                   | 0.99          | 0.06       |
| Rock               | Hey, Johnny Park!                                                                                                           | 0.99          | 0.06       |
| Rock               | I Looked At You                                                                                                             | 0.99          | 0.06       |
| Rock               | May This Be Love                                                                                                            | 0.99          | 0.06       |
| Rock               | One I Want                                                                                                                  | 0.99          | 0.06       |
| Rock               | MFC                                                                                                                         | 0.99          | 0.06       |
| Rock               | Time                                                                                                                        | 0.99          | 0.06       |
| Latin              | Jeito Faceiro                                                                                                               | 0.99          | 0.06       |
| Rock               | Hush                                                                                                                        | 0.99          | 0.06       |
| Rock               | Polly                                                                                                                       | 0.99          | 0.06       |
| Rock               | Mofo                                                                                                                        | 0.99          | 0.06       |
| Rock               | Never Say Die                                                                                                               | 0.99          | 0.06       |
| Rock               | You Fool No One                                                                                                             | 0.99          | 0.06       |
| Latin              | Jorge Da Capadócia                                                                                                          | 0.99          | 0.06       |
| Rock               | Into The Fire                                                                                                               | 0.99          | 0.06       |
| Rock               | Numb                                                                                                                        | 0.99          | 0.06       |
| Metal              | Orion                                                                                                                       | 0.99          | 0.06       |
| Metal              | The Struggle Within                                                                                                         | 0.99          | 0.06       |
| Rock               | Star A.D.                                                                                                                   | 0.99          | 0.06       |
| Rock               | New York                                                                                                                    | 0.99          | 0.06       |
| Alternative & Punk | Ava Adore                                                                                                                   | 0.99          | 0.06       |
| Rock               | Sea Of Sorrow                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Jaded                                                                                                                       | 0.99          | 0.06       |
| Rock               | Poor Tom                                                                                                                    | 0.99          | 0.06       |
| Metal              | Here I Go Again                                                                                                             | 0.99          | 0.06       |
| Metal              | Cure                                                                                                                        | 0.99          | 0.06       |
| Latin              | Maria, Maria                                                                                                                | 0.99          | 0.06       |
| Rock               | Bullet The Blue Sky                                                                                                         | 0.99          | 0.06       |
| Rock               | Beth                                                                                                                        | 0.99          | 0.06       |
| Rock               | Get Right                                                                                                                   | 0.99          | 0.06       |
| Latin              | Romaria                                                                                                                     | 0.99          | 0.06       |
| Metal              | The Four Horsemen                                                                                                           | 0.99          | 0.06       |
| Rock               | Down By The Seaside                                                                                                         | 0.99          | 0.06       |
| Alternative & Punk | Clash City Rockers                                                                                                          | 0.99          | 0.06       |
| Rock               | Travelling Riverside Blues                                                                                                  | 0.99          | 0.06       |
| Rock               | Rusty Cage                                                                                                                  | 0.99          | 0.06       |
| Rock               | Rock Das Aranhas (Ao Vivo) (Live)                                                                                           | 0.99          | 0.06       |
| Latin              | Todo Amor Que Houver Nesta Vida                                                                                             | 0.99          | 0.06       |
| Latin              | Tendo A Lua                                                                                                                 | 0.99          | 0.06       |
| Metal              | Dirty Love                                                                                                                  | 0.99          | 0.06       |
| Rock               | Stairway To Heaven                                                                                                          | 0.99          | 0.06       |
| Rock               | Where Have All The Good Times Gone?                                                                                         | 0.99          | 0.06       |
| Metal              | Seventh Son of a Seventh Son                                                                                                | 0.99          | 0.06       |
| Metal              | Faceless                                                                                                                    | 0.99          | 0.06       |
| Rock               | Do It For The Kids                                                                                                          | 0.99          | 0.06       |
| Rock               | Cropduster                                                                                                                  | 0.99          | 0.06       |
| Rock               | I Don't Know                                                                                                                | 0.99          | 0.06       |
| Metal              | Don't Cry                                                                                                                   | 0.99          | 0.06       |
| Latin              | Funk Hum                                                                                                                    | 0.99          | 0.06       |
| Rock               | Mean Disposition                                                                                                            | 0.99          | 0.06       |
| Rock               | Time Is On My Side                                                                                                          | 0.99          | 0.06       |
| Rock               | Paradise City                                                                                                               | 0.99          | 0.06       |
| Alternative & Punk | Perfect Circle                                                                                                              | 0.99          | 0.06       |
| Rock               | Let's See Action                                                                                                            | 0.99          | 0.06       |
| Rock               | Where The River Goes                                                                                                        | 0.99          | 0.06       |
| Rock               | Green Disease                                                                                                               | 0.99          | 0.06       |
| Rock               | God Gave Rock 'n' Roll To You                                                                                               | 0.99          | 0.06       |
| Metal              | Blood In The Wall                                                                                                           | 0.99          | 0.06       |
| Alternative & Punk | This Is Radio Clash                                                                                                         | 0.99          | 0.06       |
| Alternative & Punk | Low                                                                                                                         | 0.99          | 0.06       |
| Alternative & Punk | Ashes To Ashes                                                                                                              | 0.99          | 0.06       |
| Metal              | No Prayer For The Dying                                                                                                     | 0.99          | 0.06       |
| Rock               | O Dia Em Que A Terra Parou                                                                                                  | 0.99          | 0.06       |
| Metal              | Hallowed Be Thy Name                                                                                                        | 0.99          | 0.06       |
| Rock               | Strutter                                                                                                                    | 0.99          | 0.06       |
| Rock               | Outshined                                                                                                                   | 0.99          | 0.06       |
| Latin              | Todo Amor (Asas Da Liberdade)                                                                                               | 0.99          | 0.06       |
| Rock               | Loving You Sunday Morning                                                                                                   | 0.99          | 0.06       |
| Rock               | You Got Me Rocking                                                                                                          | 0.99          | 0.06       |
| Rock               | Sex Type Thing                                                                                                              | 0.99          | 0.06       |
| Rock               | Knocking At Your Back Door                                                                                                  | 0.99          | 0.06       |
| Latin              | Queixa                                                                                                                      | 0.99          | 0.06       |
| Rock               | Plush                                                                                                                       | 0.99          | 0.06       |
| Alternative & Punk | Me In Honey                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | A Small Victory                                                                                                             | 0.99          | 0.06       |
| Rock               | Love Removal Machine                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Know Your Rights                                                                                                            | 0.99          | 0.06       |
| Rock               | Heart In Your Hand                                                                                                          | 0.99          | 0.06       |
| Metal              | Ride The Lightning                                                                                                          | 0.99          | 0.06       |
| Latin              | Muita Bobeira                                                                                                               | 0.99          | 0.06       |
| Latin              | Com Açúcar E Com Afeto                                                                                                      | 0.99          | 0.06       |
| Latin              | Palco                                                                                                                       | 0.99          | 0.06       |
| Rock               | Seconds                                                                                                                     | 0.99          | 0.06       |
| Rock               | Dazed And Confused                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | RV                                                                                                                          | 0.99          | 0.06       |
| Latin              | Panis Et Circenses                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | Papeau Nuky Doe                                                                                                             | 0.99          | 0.06       |
| Metal              | Lost in Hollywood                                                                                                           | 0.99          | 0.06       |
| Rock               | So Fast, So Numb                                                                                                            | 0.99          | 0.06       |
| Metal              | Sad Statue                                                                                                                  | 0.99          | 0.06       |
| Rock               | Long As I Can See The Light                                                                                                 | 0.99          | 0.06       |
| Rock               | Down On The Corner                                                                                                          | 0.99          | 0.06       |
| Latin              | Tudo Bem                                                                                                                    | 0.99          | 0.06       |
| Rock               | Bass Trap                                                                                                                   | 0.99          | 0.06       |
| Rock               | Hot Dog                                                                                                                     | 0.99          | 0.06       |
| Latin              | A Menina Dança                                                                                                              | 0.99          | 0.06       |
| Rock               | Little Guitars (Intro)                                                                                                      | 0.99          | 0.06       |
| Latin              | Nervosa                                                                                                                     | 0.99          | 0.06       |
| Latin              | Chão de Giz (Elba Ramalho)                                                                                                  | 0.99          | 0.06       |
| Rock               | You Shook Me(2)                                                                                                             | 0.99          | 0.06       |
| Rock               | Blind Man                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Homem Primata (Vinheta)                                                                                                     | 0.99          | 0.06       |
| Rock               | Iron Maiden                                                                                                                 | 0.99          | 0.06       |
| Rock               | Fat Bottomed Girls                                                                                                          | 0.99          | 0.06       |
| Metal              | Run To The Hills                                                                                                            | 0.99          | 0.06       |
| Rock               | Ghost                                                                                                                       | 0.99          | 0.06       |
| Metal              | 2 X 4                                                                                                                       | 0.99          | 0.06       |
| Latin              | Um Indio                                                                                                                    | 0.99          | 0.06       |
| Rock               | Flower                                                                                                                      | 0.99          | 0.06       |
| Latin              | Lanterna Dos Afogados                                                                                                       | 0.99          | 0.06       |
| Rock               | No Quarter                                                                                                                  | 0.99          | 0.06       |
| Alternative & Punk | Sonifera Ilha                                                                                                               | 0.99          | 0.06       |
| Rock               | I Like Dirt                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Lucky 13                                                                                                                    | 0.99          | 0.06       |
| Metal              | Machine Men                                                                                                                 | 0.99          | 0.06       |
| Alternative & Punk | Drown Me Slowly                                                                                                             | 0.99          | 0.06       |
| Rock               | Yahweh                                                                                                                      | 0.99          | 0.06       |
| Rock               | Communication Breakdown                                                                                                     | 0.99          | 0.06       |
| Rock               | Ghost Of The Navigator                                                                                                      | 0.99          | 0.06       |
| Alternative & Punk | Lazy Gun                                                                                                                    | 0.99          | 0.06       |
| Metal              | Astronomy                                                                                                                   | 0.99          | 0.06       |
| Alternative & Punk | Falling To Pieces                                                                                                           | 0.99          | 0.06       |
| Rock               | Love Rescue Me                                                                                                              | 0.99          | 0.06       |
| Metal              | Invaders                                                                                                                    | 0.99          | 0.06       |
| Rock               | Rock Of Ages                                                                                                                | 0.99          | 0.06       |
| Metal              | I Am                                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Naked In Front Of The Computer                                                                                              | 0.99          | 0.06       |
| Latin              | Da Lama Ao Caos                                                                                                             | 0.99          | 0.06       |
| Rock               | Edie (Ciao Baby)                                                                                                            | 0.99          | 0.06       |
| Latin              | Caso Você Queira Saber                                                                                                      | 0.99          | 0.06       |
| Rock               | All Dead, All Dead                                                                                                          | 0.99          | 0.06       |
| Rock               | Free Me                                                                                                                     | 0.99          | 0.06       |
| Latin              | Me Deixas Louca                                                                                                             | 0.99          | 0.06       |
| Rock               | Mãe Terra                                                                                                                   | 0.99          | 0.06       |
| Rock               | Everything I Need                                                                                                           | 0.99          | 0.06       |
| Latin              | Coração De Estudante                                                                                                        | 0.99          | 0.06       |
| Metal              | Until It Sleeps                                                                                                             | 0.99          | 0.06       |
| Rock               | Headspace                                                                                                                   | 0.99          | 0.06       |
| Rock               | Sweetest Thing                                                                                                              | 0.99          | 0.06       |
| Alternative & Punk | Pretty Persuasion                                                                                                           | 0.99          | 0.06       |
| Rock               | Do You Like The Way                                                                                                         | 0.99          | 0.06       |
| Latin              | Terra                                                                                                                       | 0.99          | 0.06       |
| Rock               | I Still Haven't Found What I'm Looking for                                                                                  | 0.99          | 0.06       |
| Latin              | Interlude Zumbi                                                                                                             | 0.99          | 0.06       |
| Latin              | Beija-Flor                                                                                                                  | 0.99          | 0.06       |
| Rock               | White Feather                                                                                                               | 0.99          | 0.06       |
| Rock               | Always With Me, Always With You                                                                                             | 0.99          | 0.06       |
| Rock               | Don't Stand so Close to Me                                                                                                  | 0.99          | 0.06       |
| Rock               | The Playboy Mansion                                                                                                         | 0.99          | 0.06       |
| Rock               | Shining In The Light                                                                                                        | 0.99          | 0.06       |
| Alternative & Punk | Eye                                                                                                                         | 0.99          | 0.06       |
| Metal              | Only the Good Die Young                                                                                                     | 0.99          | 0.06       |
| Metal              | The Evil That Men Do                                                                                                        | 0.99          | 0.06       |
| Rock               | Rock & Roll                                                                                                                 | 0.99          | 0.06       |
| Metal              | 2 Minutes To Midnight                                                                                                       | 0.99          | 0.06       |
| Rock               | Sometimes I Feel Like Screaming                                                                                             | 0.99          | 0.06       |
| Rock               | Shout It Out Loud                                                                                                           | 0.99          | 0.06       |
| Metal              | Believer                                                                                                                    | 0.99          | 0.06       |
| Rock               | Lodi                                                                                                                        | 0.99          | 0.06       |
| Metal              | To Tame A Land                                                                                                              | 0.99          | 0.06       |
| Metal              | Shotgun Blues                                                                                                               | 0.99          | 0.06       |
| Rock               | Problem Child                                                                                                               | 0.99          | 0.06       |
| Rock               | Get Down, Make Love                                                                                                         | 0.99          | 0.06       |
| Rock               | Wearing And Tearing                                                                                                         | 0.99          | 0.06       |
| Rock               | Seven Seas Of Rhye                                                                                                          | 0.99          | 0.06       |
| Alternative & Punk | They're Red Hot                                                                                                             | 0.99          | 0.06       |
| Rock               | No Fundo Do Quintal Da Escola                                                                                               | 0.99          | 0.06       |
| Latin              | Seis Da Tarde                                                                                                               | 0.99          | 0.06       |
| Rock               | Tombstone Shadow                                                                                                            | 0.99          | 0.06       |
| Latin              | Sapopemba e Maxambomba                                                                                                      | 0.99          | 0.06       |
| Rock               | Breaking The Rules                                                                                                          | 0.99          | 0.06       |
| Latin              | Saudade Dos Aviões Da Panair (Conversando No Bar)                                                                           | 0.99          | 0.06       |
| Rock               | Intro                                                                                                                       | 0.99          | 0.06       |
| Latin              | Segue O Seco                                                                                                                | 0.99          | 0.06       |
| Rock               | Electrolite                                                                                                                 | 0.99          | 0.06       |
| Latin              | A Cura                                                                                                                      | 0.99          | 0.06       |
| Rock               | Stairway To Heaven                                                                                                          | 0.99          | 0.06       |

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
| genre_name        | track_name                                                                                                    | total_revenue | percentage |
|-------------------|---------------------------------------------------------------------------------------------------------------|---------------|------------|
| TV Shows          | Walkabout                                                                                                     | 3.98          | 0.65       |
| TV Shows          | Gay Witch Hunt                                                                                                | 3.98          | 0.65       |
| TV Shows          | Pilot                                                                                                         | 3.98          | 0.65       |
| Drama             | The Fix                                                                                                       | 3.98          | 0.65       |
| Comedy            | Phyllis's Wedding                                                                                             | 3.98          | 0.65       |
| TV Shows          | Hot Girl                                                                                                      | 3.98          | 0.65       |
| Science Fiction   | The Woman King                                                                                                | 3.98          | 0.65       |
| Drama             | How to Stop an Exploding Man                                                                                  | 3.98          | 0.65       |
| Comedy            | Producer's Cut: The Return                                                                                    | 1.99          | 0.32       |
| TV Shows          | Michael's Birthday                                                                                            | 1.99          | 0.32       |
| Drama             | Seven Minutes to Midnight                                                                                     | 1.99          | 0.32       |
| Drama             | Exposé                                                                                                        | 1.99          | 0.32       |
| TV Shows          | Genesis                                                                                                       | 1.99          | 0.32       |
| Drama             | Something Nice Back Home                                                                                      | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Magnificent Warriors                                                                                      | 1.99          | 0.32       |
| Drama             | The Man Behind the Curtain                                                                                    | 1.99          | 0.32       |
| TV Shows          | The Carpet                                                                                                    | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Crossroads, Pt. 2                                                                                             | 1.99          | 0.32       |
| Drama             | Catch-22                                                                                                      | 1.99          | 0.32       |
| Drama             | There's No Place Like Home, Pt. 3                                                                             | 1.99          | 0.32       |
| Drama             | Company Man                                                                                                   | 1.99          | 0.32       |
| TV Shows          | The Dundies                                                                                                   | 1.99          | 0.32       |
| Drama             | Enter 77                                                                                                      | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Lost Planet of the Gods, Pt. 1                                                                                | 1.99          | 0.32       |
| Drama             | The Whole Truth                                                                                               | 1.99          | 0.32       |
| Science Fiction   | A Day In the Life                                                                                             | 1.99          | 0.32       |
| Comedy            | The Convict                                                                                                   | 1.99          | 0.32       |
| Drama             | The Hard Part                                                                                                 | 1.99          | 0.32       |
| TV Shows          | The Coup                                                                                                      | 1.99          | 0.32       |
| TV Shows          | Dave                                                                                                          | 1.99          | 0.32       |
| TV Shows          | The 23rd Psalm                                                                                                | 1.99          | 0.32       |
| TV Shows          | "?"                                                                                                           | 1.99          | 0.32       |
| TV Shows          | The Long Con                                                                                                  | 1.99          | 0.32       |
| Drama             | One Giant Leap                                                                                                | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Hand of God                                                                                               | 1.99          | 0.32       |
| Drama             | Parasite                                                                                                      | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Greetings from Earth, Pt. 2                                                                                   | 1.99          | 0.32       |
| TV Shows          | Man of Science, Man of Faith (Premiere)                                                                       | 1.99          | 0.32       |
| Comedy            | Back from Vacation                                                                                            | 1.99          | 0.32       |
| Comedy            | A Benihana Christmas, Pts. 1 & 2                                                                              | 1.99          | 0.32       |
| TV Shows          | Exodus, Pt. 2                                                                                                 | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Lost Warrior                                                                                              | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Living Legend, Pt. 2                                                                                      | 1.99          | 0.32       |
| Drama             | Past, Present, and Future                                                                                     | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Long Patrol                                                                                               | 1.99          | 0.32       |
| TV Shows          | Solitary                                                                                                      | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Experiment In Terra                                                                                           | 1.99          | 0.32       |
| TV Shows          | Orientation                                                                                                   | 1.99          | 0.32       |
| TV Shows          | Nothing to Hide                                                                                               | 1.99          | 0.32       |
| Drama             | Through the Looking Glass, Pt. 1                                                                              | 1.99          | 0.32       |
| TV Shows          | The Initiation                                                                                                | 1.99          | 0.32       |
| Drama             | Distractions                                                                                                  | 1.99          | 0.32       |
| Drama             | The Beginning of the End                                                                                      | 1.99          | 0.32       |
| Science Fiction   | Hero                                                                                                          | 1.99          | 0.32       |
| Science Fiction   | Unfinished Business                                                                                           | 1.99          | 0.32       |
| Drama             | Lost Survival Guide                                                                                           | 1.99          | 0.32       |
| TV Shows          | Email Surveillance                                                                                            | 1.99          | 0.32       |
| Drama             | The Glass Ballerina                                                                                           | 1.99          | 0.32       |
| TV Shows          | Ji Yeon                                                                                                       | 1.99          | 0.32       |
| TV Shows          | Occupation / Precipice                                                                                        | 1.99          | 0.32       |
| TV Shows          | I Do                                                                                                          | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Crossroads, Pt. 1                                                                                             | 1.99          | 0.32       |
| TV Shows          | Exodus, Pt. 1                                                                                                 | 1.99          | 0.32       |
| TV Shows          | The Convention                                                                                                | 1.99          | 0.32       |
| TV Shows          | The Other 48 Days                                                                                             | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Lost Planet of the Gods, Pt. 2                                                                                | 1.99          | 0.32       |
| Drama             | The Economist                                                                                                 | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Living Legend, Pt. 1                                                                                      | 1.99          | 0.32       |
| Comedy            | The Job                                                                                                       | 1.99          | 0.32       |
| TV Shows          | Deus Ex Machina                                                                                               | 1.99          | 0.32       |
| TV Shows          | Halloween                                                                                                     | 1.99          | 0.32       |
| TV Shows          | Diwali                                                                                                        | 1.99          | 0.32       |
| TV Shows          | Exodus (Part 2) [Season Finale]                                                                               | 1.99          | 0.32       |
| TV Shows          | House of the Rising Sun                                                                                       | 1.99          | 0.32       |
| Comedy            | Safety Training                                                                                               | 1.99          | 0.32       |
| TV Shows          | Christmas Party                                                                                               | 1.99          | 0.32       |
| Drama             | Stranger In a Strange Land                                                                                    | 1.99          | 0.32       |
| TV Shows          | Branch Closing                                                                                                | 1.99          | 0.32       |
| TV Shows          | ...And Found                                                                                                  | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Gun On Ice Planet Zero, Pt. 1                                                                             | 1.99          | 0.32       |
| Drama             | Through a Looking Glass                                                                                       | 1.99          | 0.32       |
| Sci Fi & Fantasy  | The Gun On Ice Planet Zero, Pt. 2                                                                             | 1.99          | 0.32       |
| TV Shows          | Homecoming                                                                                                    | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Greetings from Earth, Pt. 1                                                                                   | 1.99          | 0.32       |
| TV Shows          | Born to Run                                                                                                   | 1.99          | 0.32       |
| TV Shows          | Collaborators                                                                                                 | 1.99          | 0.32       |
| Science Fiction   | The Passage                                                                                                   | 1.99          | 0.32       |
| Drama             | Par Avion                                                                                                     | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Take the Celestra                                                                                             | 1.99          | 0.32       |
| Comedy            | Branch Closing                                                                                                | 1.99          | 0.32       |
| TV Shows          | Outlaws                                                                                                       | 1.99          | 0.32       |
| TV Shows          | Adrift                                                                                                        | 1.99          | 0.32       |
| TV Shows          | Meet Kevin Johnson                                                                                            | 1.99          | 0.32       |
| Drama             | Better Halves                                                                                                 | 1.99          | 0.32       |
| Sci Fi & Fantasy  | War of the Gods, Pt. 2                                                                                        | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Baltar's Escape                                                                                               | 1.99          | 0.32       |
| TV Shows          | Diversity Day                                                                                                 | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Battlestar Galactica, Pt. 1                                                                                   | 1.99          | 0.32       |
| Sci Fi & Fantasy  | Battlestar Galactica, Pt. 2                                                                                   | 1.99          | 0.32       |
| Drama             | Live Together, Die Alone, Pt. 1                                                                               | 1.99          | 0.32       |
| TV Shows          | S.O.S.                                                                                                        | 1.99          | 0.32       |
| Drama             | Fire + Water                                                                                                  | 1.99          | 0.32       |
| TV Shows          | The Moth                                                                                                      | 1.99          | 0.32       |
| Jazz              | Lamento De Carnaval                                                                                           | 1.98          | 0.32       |
| Blues             | Title Song                                                                                                    | 1.98          | 0.32       |
| Blues             | Promises                                                                                                      | 1.98          | 0.32       |
| Classical         | String Quartet No. 12 in C Minor, D. 703 "Quartettsatz": II. Andante - Allegro assai                          | 1.98          | 0.32       |
| R&B/Soul          | Rehab                                                                                                         | 1.98          | 0.32       |
| Pop               | Beautiful Boy                                                                                                 | 1.98          | 0.32       |
| Jazz              | End Of Romanticism                                                                                            | 1.98          | 0.32       |
| Hip Hop/Rap       | Nega Do Cabelo Duro                                                                                           | 1.98          | 0.32       |
| Jazz              | Lemon Drop                                                                                                    | 1.98          | 0.32       |
| R&B/Soul          | Save The Children                                                                                             | 1.98          | 0.32       |
| Hip Hop/Rap       | Rappers Reais                                                                                                 | 1.98          | 0.32       |
| Classical         | Scheherazade, Op. 35: I. The Sea and Sindbad's Ship                                                           | 1.98          | 0.32       |
| Jazz              | The Duke                                                                                                      | 1.98          | 0.32       |
| Jazz              | Por Causa De Você                                                                                             | 1.98          | 0.32       |
| Blues             | When My Left Eye Jumps                                                                                        | 1.98          | 0.32       |
| Jazz              | J Squared                                                                                                     | 1.98          | 0.32       |
| Blues             | Sunshine Of Your Love                                                                                         | 1.98          | 0.32       |
| Jazz              | Surrender                                                                                                     | 1.98          | 0.32       |
| Blues             | Lay Down Sally                                                                                                | 1.98          | 0.32       |
| Blues             | Midnight From The Inside Out                                                                                  | 1.98          | 0.32       |
| Reggae            | A Cor Do Sol                                                                                                  | 1.98          | 0.32       |
| Classical         | Symphonie Fantastique, Op. 14: V. Songe d'une nuit du sabbat                                                  | 1.98          | 0.32       |
| R&B/Soul          | Abraham, Martin And John                                                                                      | 1.98          | 0.32       |
| Jazz              | Drum Boogie                                                                                                   | 1.98          | 0.32       |
| Reggae            | C'est La Vie                                                                                                  | 1.98          | 0.32       |
| Blues             | Lonely Stranger                                                                                               | 1.98          | 0.32       |
| Classical         | Suite No. 3 in D, BWV 1068: III. Gavotte I & II                                                               | 1.98          | 0.32       |
| Pop               | Give Peace a Chance                                                                                           | 1.98          | 0.32       |
| R&B/Soul          | Hey America                                                                                                   | 1.98          | 0.32       |
| Jazz              | Don't Take Your Love From Me                                                                                  | 1.98          | 0.32       |
| Electronica/Dance | Light Years                                                                                                   | 1.98          | 0.32       |
| Classical         | Music for the Funeral of Queen Mary: VI. "Thou Knowest, Lord, the Secrets of Our Hearts"                      | 1.98          | 0.32       |
| Blues             | Travis Walk                                                                                                   | 1.98          | 0.32       |
| Soundtrack        | Plot 180                                                                                                      | 1.98          | 0.32       |
| Jazz              | Starburst                                                                                                     | 1.98          | 0.32       |
| Jazz              | Blue Rythm Fantasy                                                                                            | 1.98          | 0.32       |
| Jazz              | L'Arc En Ciel De Miles                                                                                        | 1.98          | 0.32       |
| Bossa Nova        | Onde Anda Você                                                                                                | 1.98          | 0.32       |
| Soundtrack        | Slug                                                                                                          | 0.99          | 0.16       |
| Blues             | Leave My Girl Alone                                                                                           | 0.99          | 0.16       |
| Blues             | Leave My Girl Alone                                                                                           | 0.99          | 0.16       |
| Jazz              | Bye Bye Blackbird                                                                                             | 0.99          | 0.16       |
| Bossa Nova        | Samba Da Volta                                                                                                | 0.99          | 0.16       |
| Alternative       | Scar On the Sky                                                                                               | 0.99          | 0.16       |
| World             | O Que Vai Em Meu Coração                                                                                      | 0.99          | 0.16       |
| Soundtrack        | Leandro De Itaquera 2001                                                                                      | 0.99          | 0.16       |
| Alternative       | Billie Jean                                                                                                   | 0.99          | 0.16       |
| Jazz              | Thinking 'Bout Tomorrow                                                                                       | 0.99          | 0.16       |
| Classical         | Two Fanfares for Orchestra: II. Short Ride in a Fast Machine                                                  | 0.99          | 0.16       |
| World             | Cafezinho                                                                                                     | 0.99          | 0.16       |
| Reggae            | Don't Look Back                                                                                               | 0.99          | 0.16       |
| Pop               | F**k Me Pumps                                                                                                 | 0.99          | 0.16       |
| Pop               | I Heard Love Is Blind                                                                                         | 0.99          | 0.16       |
| Pop               | God                                                                                                           | 0.99          | 0.16       |
| Soundtrack        | Camisa Verde 2001                                                                                             | 0.99          | 0.16       |
| Jazz              | Little Linda                                                                                                  | 0.99          | 0.16       |
| Classical         | Piano Sonata No. 14 in C Sharp Minor, Op. 27, No. 2, "Moonlight": I. Adagio sostenuto                         | 0.99          | 0.16       |
| Pop               | Cold Turkey                                                                                                   | 0.99          | 0.16       |
| Blues             | Hey Hey                                                                                                       | 0.99          | 0.16       |
| Blues             | High Head Blues                                                                                               | 0.99          | 0.16       |
| Blues             | First Time I Met The Blues                                                                                    | 0.99          | 0.16       |
| Jazz              | My Ship                                                                                                       | 0.99          | 0.16       |
| Blues             | 05 - Phantom of the Opera                                                                                     | 0.99          | 0.16       |
| Classical         | Wellington's Victory or the Battle Symphony, Op.91: 2. Symphony of Triumph                                    | 0.99          | 0.16       |
| Jazz              | Deep Waters                                                                                                   | 0.99          | 0.16       |
| Pop               | Help Yourself                                                                                                 | 0.99          | 0.16       |
| Jazz              | Heliopolis                                                                                                    | 0.99          | 0.16       |
| Bossa Nova        | Pot-Pourri N.º 5                                                                                              | 0.99          | 0.16       |
| Blues             | Alberta                                                                                                       | 0.99          | 0.16       |
| Blues             | Crossroads                                                                                                    | 0.99          | 0.16       |
| Jazz              | Lament                                                                                                        | 0.99          | 0.16       |
| Blues             | Layla                                                                                                         | 0.99          | 0.16       |
| Classical         | Fantasia On Greensleeves                                                                                      | 0.99          | 0.16       |
| Jazz              | Song For Lorraine                                                                                             | 0.99          | 0.16       |
| Bossa Nova        | Canto De Ossanha                                                                                              | 0.99          | 0.16       |
| Jazz              | Nefertiti                                                                                                     | 0.99          | 0.16       |
| Classical         | Act IV, Symphony                                                                                              | 0.99          | 0.16       |
| Jazz              | The Meaning Of The Blues                                                                                      | 0.99          | 0.16       |
| Reggae            | Bush Doctor                                                                                                   | 0.99          | 0.16       |
| Blues             | Layla                                                                                                         | 0.99          | 0.16       |
| Easy Listening    | Mack The Knife                                                                                                | 0.99          | 0.16       |
| World             | Demorou!                                                                                                      | 0.99          | 0.16       |
| Reggae            | Crystal Ball                                                                                                  | 0.99          | 0.16       |
| Reggae            | Wanted Dread And Alive                                                                                        | 0.99          | 0.16       |
| Jazz              | De La Luz                                                                                                     | 0.99          | 0.16       |
| Rock And Roll     | Carol                                                                                                         | 0.99          | 0.16       |
| Reggae            | Higher Ground                                                                                                 | 0.99          | 0.16       |
| Classical         | Étude 1, In C Major - Preludio (Presto) - Liszt                                                               | 0.99          | 0.16       |
| Jazz              | Best Thing                                                                                                    | 0.99          | 0.16       |
| R&B/Soul          | Living In America                                                                                             | 0.99          | 0.16       |
| Jazz              | Valentino's                                                                                                   | 0.99          | 0.16       |
| Classical         | Die Walküre: The Ride of the Valkyries                                                                        | 0.99          | 0.16       |
| Blues             | Sting Me                                                                                                      | 0.99          | 0.16       |
| Bossa Nova        | Por Que Será                                                                                                  | 0.99          | 0.16       |
| Jazz              | Jacob's Ladder                                                                                                | 0.99          | 0.16       |
| Jazz              | Do what cha wanna                                                                                             | 0.99          | 0.16       |
| Reggae            | Eu Também Quero Beijar                                                                                        | 0.99          | 0.16       |
| R&B/Soul          | Just Friends                                                                                                  | 0.99          | 0.16       |
| R&B/Soul          | You Sure Love To Ball                                                                                         | 0.99          | 0.16       |
| Pop               | Lavadeira                                                                                                     | 0.99          | 0.16       |
| Pop               | Levada do Amor (Ailoviu)                                                                                      | 0.99          | 0.16       |
| Blues             | Nobody Knows You When You're Down & Out                                                                       | 0.99          | 0.16       |
| Reggae            | Já Foi                                                                                                        | 0.99          | 0.16       |
| Alternative       | Show Me How to Live (Live at the Quart Festival)                                                              | 0.99          | 0.16       |
| Classical         | Karelia Suite, Op.11: 2. Ballade (Tempo Di Menuetto)                                                          | 0.99          | 0.16       |
| Jazz              | Blues For Pablo (Alternate Take)                                                                              | 0.99          | 0.16       |
| R&B/Soul          | He Can Only Hold Her                                                                                          | 0.99          | 0.16       |
| World             | Aos Leões                                                                                                     | 0.99          | 0.16       |
| Blues             | Scratch-N-Sniff                                                                                               | 0.99          | 0.16       |
| Alternative       | Slowness                                                                                                      | 0.99          | 0.16       |
| Alternative       | Shape of Things to Come                                                                                       | 0.99          | 0.16       |
| Reggae            | Sábado A Noite                                                                                                | 0.99          | 0.16       |
| Jazz              | So What                                                                                                       | 0.99          | 0.16       |
| Alternative       | All Night Thing                                                                                               | 0.99          | 0.16       |
| R&B/Soul          | Were Do We Go From Here                                                                                       | 0.99          | 0.16       |
| Reggae            | Onde Você Mora?                                                                                               | 0.99          | 0.16       |
| Blues             | Wall Of Denial                                                                                                | 0.99          | 0.16       |
| Hip Hop/Rap       | Put Your Head Out                                                                                             | 0.99          | 0.16       |
| Easy Listening    | Summer Love                                                                                                   | 0.99          | 0.16       |
| R&B/Soul          | Black Capricorn Day                                                                                           | 0.99          | 0.16       |
| Blues             | Old Love                                                                                                      | 0.99          | 0.16       |
| Electronica/Dance | Chapa o Coco                                                                                                  | 0.99          | 0.16       |
| Hip Hop/Rap       | Hemp Family                                                                                                   | 0.99          | 0.16       |
| Soundtrack        | Your Blue Room                                                                                                | 0.99          | 0.16       |
| Hip Hop/Rap       | Feel It                                                                                                       | 0.99          | 0.16       |
| Jazz              | Groovus Interruptus                                                                                           | 0.99          | 0.16       |
| Soundtrack        | Theme From The Swan                                                                                           | 0.99          | 0.16       |
| Classical         | Canon and Gigue in D Major: I. Canon                                                                          | 0.99          | 0.16       |
| Blues             | Miracle To Me                                                                                                 | 0.99          | 0.16       |
| Jazz              | As We Sleep                                                                                                   | 0.99          | 0.16       |
| R&B/Soul          | Planet Home                                                                                                   | 0.99          | 0.16       |
| Easy Listening    | Bad, Bad Leroy Brown                                                                                          | 0.99          | 0.16       |
| R&B/Soul          | Praise                                                                                                        | 0.99          | 0.16       |
| Reggae            | Pick Myself Up                                                                                                | 0.99          | 0.16       |
| Rock And Roll     | Long Tall Sally                                                                                               | 0.99          | 0.16       |
| Blues             | Tears In Heaven                                                                                               | 0.99          | 0.16       |
| Jazz              | Moon germs                                                                                                    | 0.99          | 0.16       |
| Classical         | Pini Di Roma (Pinien Von Rom) \ I Pini Della Via Appia                                                        | 0.99          | 0.16       |
| Heavy Metal       | Dance Of Death                                                                                                | 0.99          | 0.16       |
| World             | É Fogo                                                                                                        | 0.99          | 0.16       |
| R&B/Soul          | Tears Dry On Their Own                                                                                        | 0.99          | 0.16       |
| Electronica/Dance | Manifest Destiny                                                                                              | 0.99          | 0.16       |
| Reggae            | Na Frente Da TV                                                                                               | 0.99          | 0.16       |
| Easy Listening    | I Get A Kick Out Of You                                                                                       | 0.99          | 0.16       |
| Pop               | [Just Like] Starting Over                                                                                     | 0.99          | 0.16       |
| Pop               | #9 Dream                                                                                                      | 0.99          | 0.16       |
| Jazz              | Boogie Blues                                                                                                  | 0.99          | 0.16       |
| Alternative       | Call Me a Dog                                                                                                 | 0.99          | 0.16       |
| Blues             | Swing Low Sweet Chariot                                                                                       | 0.99          | 0.16       |
| R&B/Soul          | Papa's Got A Brand New Bag Pt.1                                                                               | 0.99          | 0.16       |
| Jazz              | Millenium                                                                                                     | 0.99          | 0.16       |
| Heavy Metal       | Another Life                                                                                                  | 0.99          | 0.16       |
| Classical         | Symphony No. 2, Op. 16 -  "The Four Temperaments": II. Allegro Comodo e Flemmatico                            | 0.99          | 0.16       |
| Reggae            | Falar A Verdade                                                                                               | 0.99          | 0.16       |
| World             | Enquanto O Dia Não Vem                                                                                        | 0.99          | 0.16       |
| Reggae            | I Would Do For You                                                                                            | 0.99          | 0.16       |
| Blues             | Riviera Paradise                                                                                              | 0.99          | 0.16       |
| Blues             | Cursed Diamonds                                                                                               | 0.99          | 0.16       |
| R&B/Soul          | Get Up Offa That Thing                                                                                        | 0.99          | 0.16       |
| Jazz              | Believe                                                                                                       | 0.99          | 0.16       |
| Soundtrack        | Esperando Na Janela                                                                                           | 0.99          | 0.16       |
| Heavy Metal       | Die With Your Boots On                                                                                        | 0.99          | 0.16       |
| World             | Equinocio                                                                                                     | 0.99          | 0.16       |
| Classical         | Jupiter, the Bringer of Jollity                                                                               | 0.99          | 0.16       |
| Pop               | Take the Box                                                                                                  | 0.99          | 0.16       |
| Electronica/Dance | Instinto Colectivo                                                                                            | 0.99          | 0.16       |
| Blues             | Black Moon Creeping                                                                                           | 0.99          | 0.16       |
| Pop               | Gimme Some Truth                                                                                              | 0.99          | 0.16       |
| Classical         | Concerto for Piano No. 2 in F Minor, Op. 21: II. Larghetto                                                    | 0.99          | 0.16       |
| Hip Hop/Rap       | O Bicho Tá Pregando                                                                                           | 0.99          | 0.16       |
| Reggae            | Here I Am (Come And Take Me)                                                                                  | 0.99          | 0.16       |
| Heavy Metal       | The Ides Of March                                                                                             | 0.99          | 0.16       |
| Easy Listening    | Come Fly With Me                                                                                              | 0.99          | 0.16       |
| Blues             | After Midnight                                                                                                | 0.99          | 0.16       |
| Bossa Nova        | Minha Namorada                                                                                                | 0.99          | 0.16       |
| Pop               | My Love                                                                                                       | 0.99          | 0.16       |
| Jazz              | Solo-Panhandler                                                                                               | 0.99          | 0.16       |
| Blues             | San Francisco Bay Blues                                                                                       | 0.99          | 0.16       |
| Soundtrack        | Ito Okashi                                                                                                    | 0.99          | 0.16       |
| Pop               | Reggae Tchan                                                                                                  | 0.99          | 0.16       |
| Reggae            | Extra                                                                                                         | 0.99          | 0.16       |
| Jazz              | Jungle Drums                                                                                                  | 0.99          | 0.16       |
| Electronica/Dance | Funk de Bamba                                                                                                 | 0.99          | 0.16       |
| Heavy Metal       | Age Of Innocence                                                                                              | 0.99          | 0.16       |
| Reggae            | Bring Me Your Cup                                                                                             | 0.99          | 0.16       |
| R&B/Soul          | Me & Mr. Jones                                                                                                | 0.99          | 0.16       |
| Classical         | Adios nonino                                                                                                  | 0.99          | 0.16       |
| Jazz              | Ligia                                                                                                         | 0.99          | 0.16       |
| Heavy Metal       | Genghis Khan                                                                                                  | 0.99          | 0.16       |
| Alternative       | Until We Fall                                                                                                 | 0.99          | 0.16       |
| Classical         | Peer Gynt Suite No.1, Op.46: 1. Morning Mood                                                                  | 0.99          | 0.16       |
| Pop               | Jealous Guy                                                                                                   | 0.99          | 0.16       |
| Classical         | Metopes, Op. 29: Calypso                                                                                      | 0.99          | 0.16       |
| Classical         | Sing Joyfully                                                                                                 | 0.99          | 0.16       |
| Electronica/Dance | Armadura                                                                                                      | 0.99          | 0.16       |
| Hip Hop/Rap       | Danny Boy, Danny Boy                                                                                          | 0.99          | 0.16       |
| Reggae            | Wear You To The Ball                                                                                          | 0.99          | 0.16       |
| Jazz              | Jean Pierre (Live)                                                                                            | 0.99          | 0.16       |
| Bossa Nova        | Pot-Pourri N.º 2                                                                                              | 0.99          | 0.16       |
| Pop               | Tapa Aqui, Descobre Ali                                                                                       | 0.99          | 0.16       |
| Jazz              | Rasul                                                                                                         | 0.99          | 0.16       |
| Electronica/Dance | Um Lugar ao Sol                                                                                               | 0.99          | 0.16       |
| Blues             | 04 - Running Free                                                                                             | 0.99          | 0.16       |
| Jazz              | Angela                                                                                                        | 0.99          | 0.16       |
| Reggae            | Pensamento                                                                                                    | 0.99          | 0.16       |
| Bossa Nova        | Formosa                                                                                                       | 0.99          | 0.16       |
| Alternative       | Sound of a Gun                                                                                                | 0.99          | 0.16       |
| World             | No Futuro                                                                                                     | 0.99          | 0.16       |
| Pop               | Gimme Some Truth                                                                                              | 0.99          | 0.16       |
| Blues             | Wonderful Tonight                                                                                             | 0.99          | 0.16       |
| Blues             | Bell Bottom Blues                                                                                             | 0.99          | 0.16       |
| Jazz              | She Wears Black                                                                                               | 0.99          | 0.16       |
| Jazz              | Opus No.1                                                                                                     | 0.99          | 0.16       |
| Blues             | Let Me Love You Baby                                                                                          | 0.99          | 0.16       |
| Hip Hop/Rap       | Guess Who's Back                                                                                              | 0.99          | 0.16       |
| Blues             | Signe                                                                                                         | 0.99          | 0.16       |
| Blues             | Soul Singing                                                                                                  | 0.99          | 0.16       |
| World             | Din Din Wo (Little Child)                                                                                     | 0.99          | 0.16       |
| Jazz              | Otay                                                                                                          | 0.99          | 0.16       |
| World             | Papelão                                                                                                       | 0.99          | 0.16       |
| Bossa Nova        | Pot-Pourri N.º 4                                                                                              | 0.99          | 0.16       |
| Reggae            | Jah Seh No                                                                                                    | 0.99          | 0.16       |
| R&B/Soul          | Wake Up Alone                                                                                                 | 0.99          | 0.16       |
| R&B/Soul          | Destitute Illusions                                                                                           | 0.99          | 0.16       |
| Blues             | 01 - Prowler                                                                                                  | 0.99          | 0.16       |
| Jazz              | Spanish moss-"A sound portrait"-Spanish moss                                                                  | 0.99          | 0.16       |
| Jazz              | It Doesn't Matter                                                                                             | 0.99          | 0.16       |
| Soundtrack        | Beach Sequence                                                                                                | 0.99          | 0.16       |
| Rock And Roll     | Rock 'N' Roll Music                                                                                           | 0.99          | 0.16       |
| Electronica/Dance | Chega no Suingue                                                                                              | 0.99          | 0.16       |
| Blues             | Let It Grow                                                                                                   | 0.99          | 0.16       |
| Pop               | Imagine                                                                                                       | 0.99          | 0.16       |
| Soundtrack        | Miss Sarajevo                                                                                                 | 0.99          | 0.16       |
| Classical         | Sonata for Solo Violin: IV: Presto                                                                            | 0.99          | 0.16       |
| Hip Hop/Rap       | Salutations                                                                                                   | 0.99          | 0.16       |
| Hip Hop/Rap       | Se Liga                                                                                                       | 0.99          | 0.16       |
| Jazz              | Up An' Atom                                                                                                   | 0.99          | 0.16       |
| R&B/Soul          | Say It Loud, I'm Black And I'm Proud Pt.1                                                                     | 0.99          | 0.16       |
| Easy Listening    | It Was A Very Good Year                                                                                       | 0.99          | 0.16       |
| Jazz              | Colibri                                                                                                       | 0.99          | 0.16       |
| R&B/Soul          | You Know I'm No Good (feat. Ghostface Killah)                                                                 | 0.99          | 0.16       |
| Classical         | The Messiah: Behold, I Tell You a Mystery... The Trumpet Shall Sound                                          | 0.99          | 0.16       |
| Jazz              | Overtime                                                                                                      | 0.99          | 0.16       |
| R&B/Soul          | Back to Black                                                                                                 | 0.99          | 0.16       |
| World             | Já Foi                                                                                                        | 0.99          | 0.16       |
| Rock And Roll     | C'Mon Everybody                                                                                               | 0.99          | 0.16       |
| Classical         | A Midsummer Night's Dream, Op.61 Incidental Music: No.7 Notturno                                              | 0.99          | 0.16       |
| World             | Voce Inteira                                                                                                  | 0.99          | 0.16       |
| R&B/Soul          | Rehab (Hot Chip Remix)                                                                                        | 0.99          | 0.16       |
| Rock And Roll     | Money                                                                                                         | 0.99          | 0.16       |
| Pop               | Intro / Stronger Than Me                                                                                      | 0.99          | 0.16       |
| Reggae            | Podes Crer                                                                                                    | 0.99          | 0.16       |
| Blues             | Let Me Love You Baby                                                                                          | 0.99          | 0.16       |
| R&B/Soul          | King For A Day                                                                                                | 0.99          | 0.16       |
| R&B/Soul          | It's A Man's Man's Man's World                                                                                | 0.99          | 0.16       |
| Pop               | Imagine                                                                                                       | 0.99          | 0.16       |
| Easy Listening    | New York, New York                                                                                            | 0.99          | 0.16       |
| Pop               | Oh, My Love                                                                                                   | 0.99          | 0.16       |
| Jazz              | Falando De Amor                                                                                               | 0.99          | 0.16       |
| Blues             | Walkin' Blues                                                                                                 | 0.99          | 0.16       |
| R&B/Soul          | I'm Real                                                                                                      | 0.99          | 0.16       |
| Blues             | Before You Accuse Me                                                                                          | 0.99          | 0.16       |
| Blues             | Knockin On Heavens Door                                                                                       | 0.99          | 0.16       |
| Jazz              | Baltimore, DC                                                                                                 | 0.99          | 0.16       |
| Heavy Metal       | Phantom Of The Opera                                                                                          | 0.99          | 0.16       |
| Jazz              | The Pan Piper                                                                                                 | 0.99          | 0.16       |
| R&B/Soul          | Out Of Sight                                                                                                  | 0.99          | 0.16       |
| Jazz              | Canta, Canta Mais                                                                                             | 0.99          | 0.16       |
| R&B/Soul          | Soul Education                                                                                                | 0.99          | 0.16       |
| Blues             | Remedy                                                                                                        | 0.99          | 0.16       |
| R&B/Soul          | Heavy Love Affair                                                                                             | 0.99          | 0.16       |
| Easy Listening    | Fly Me To The Moon                                                                                            | 0.99          | 0.16       |
| Jazz              | Let Me Off Uptown                                                                                             | 0.99          | 0.16       |
| Jazz              | When Evening Falls                                                                                            | 0.99          | 0.16       |
| Jazz              | Showcase                                                                                                      | 0.99          | 0.16       |
| Classical         | Romeo et Juliette: No. 11 - Danse des Chevaliers                                                              | 0.99          | 0.16       |
| R&B/Soul          | Deeper Underground                                                                                            | 0.99          | 0.16       |
| Rock And Roll     | Good Golly Miss Molly                                                                                         | 0.99          | 0.16       |
| Jazz              | Black Satin                                                                                                   | 0.99          | 0.16       |
| Soundtrack        | Pau-De-Arara                                                                                                  | 0.99          | 0.16       |
| Reggae            | Firmamento                                                                                                    | 0.99          | 0.16       |
| Jazz              | How High The Moon                                                                                             | 0.99          | 0.16       |
| Blues             | 09 - Iron Maiden                                                                                              | 0.99          | 0.16       |
| Alternative       | Safe and Sound                                                                                                | 0.99          | 0.16       |
| Classical         | Requiem, Op.48: 4. Pie Jesu                                                                                   | 0.99          | 0.16       |
| Heavy Metal       | Wildest Dreams                                                                                                | 0.99          | 0.16       |
| Blues             | My Time After Awhile                                                                                          | 0.99          | 0.16       |
| R&B/Soul          | You've Been A Long Time Coming                                                                                | 0.99          | 0.16       |
| Alternative       | Moth                                                                                                          | 0.99          | 0.16       |
| Classical         | Concerto for Cello and Orchestra in E minor, Op. 85: I. Adagio - Moderato                                     | 0.99          | 0.16       |
| Jazz              | Compulsion                                                                                                    | 0.99          | 0.16       |
| Easy Listening    | What Now My Love                                                                                              | 0.99          | 0.16       |
| Alternative       | Disappearing Act                                                                                              | 0.99          | 0.16       |
| Hip Hop/Rap       | Hip Hop Rio                                                                                                   | 0.99          | 0.16       |
| Heavy Metal       | Face In The Sand                                                                                              | 0.99          | 0.16       |
| World             | A Moça e a Chuva                                                                                              | 0.99          | 0.16       |
| Reggae            | Onde Você Mora?                                                                                               | 0.99          | 0.16       |
| Classical         | Prometheus Overture, Op. 43                                                                                   | 0.99          | 0.16       |
| Pop               | Instant Karma                                                                                                 | 0.99          | 0.16       |
| Jazz              | O Boto (Bôto)                                                                                                 | 0.99          | 0.16       |
| Heavy Metal       | Drifter                                                                                                       | 0.99          | 0.16       |
| Classical         | Symphony No. 2: III. Allegro vivace                                                                           | 0.99          | 0.16       |
| Jazz              | I Don't Wanna Be Kissed (By Anyone But You)                                                                   | 0.99          | 0.16       |
| Soundtrack        | Morro Da Casa Verde 2001                                                                                      | 0.99          | 0.16       |
| Jazz              | Bop Boogie                                                                                                    | 0.99          | 0.16       |
| Bossa Nova        | Berimbau                                                                                                      | 0.99          | 0.16       |
| Soundtrack        | Juazeiro                                                                                                      | 0.99          | 0.16       |
| R&B/Soul          | Seek And You Shall Find                                                                                       | 0.99          | 0.16       |
| R&B/Soul          | Some Unholy War                                                                                               | 0.99          | 0.16       |
| Hip Hop/Rap       | Top O' The Morning To Ya                                                                                      | 0.99          | 0.16       |
| Classical         | Symphony No. 3 Op. 36 for Orchestra and Soprano "Symfonia Piesni Zalosnych" \ Lento E Largo - Tranquillissimo | 0.99          | 0.16       |
| R&B/Soul          | You Know I'm No Good                                                                                          | 0.99          | 0.16       |
| Bossa Nova        | Como É Duro Trabalhar                                                                                         | 0.99          | 0.16       |
| Soundtrack        | X-9 2001                                                                                                      | 0.99          | 0.16       |
| Classical         | Partita in E Major, BWV 1006A: I. Prelude                                                                     | 0.99          | 0.16       |
| Electronica/Dance | Todo o Carnaval tem seu Fim                                                                                   | 0.99          | 0.16       |
| R&B/Soul          | When I Had Your Love                                                                                          | 0.99          | 0.16       |
| R&B/Soul          | Night Train                                                                                                   | 0.99          | 0.16       |
| Reggae            | Homely Girl                                                                                                   | 0.99          | 0.16       |
| Soundtrack        | Gavioes 2001                                                                                                  | 0.99          | 0.16       |
| Soundtrack        | Ipiranga 2001                                                                                                 | 0.99          | 0.16       |
| Reggae            | Doutor                                                                                                        | 0.99          | 0.16       |
| Jazz              | Outbreak                                                                                                      | 0.99          | 0.16       |
| Jazz              | Playtime                                                                                                      | 0.99          | 0.16       |
| Heavy Metal       | Purgatory                                                                                                     | 0.99          | 0.16       |
| Jazz              | 'Round Midnight                                                                                               | 0.99          | 0.16       |
| Blues             | Crossfire                                                                                                     | 0.99          | 0.16       |
| Classical         | Symphony No. 104 in D Major "London": IV. Finale: Spiritoso                                                   | 0.99          | 0.16       |
| Blues             | Badge                                                                                                         | 0.99          | 0.16       |
| Blues             | Girl From A Pawnshop                                                                                          | 0.99          | 0.16       |
| Hip Hop/Rap       | Bossa                                                                                                         | 0.99          | 0.16       |
| Blues             | Stone Crazy                                                                                                   | 0.99          | 0.16       |
| Reggae            | Firmamento                                                                                                    | 0.99          | 0.16       |
| R&B/Soul          | It's Too Funky In Here                                                                                        | 0.99          | 0.16       |
| Bossa Nova        | Carta Ao Tom 74                                                                                               | 0.99          | 0.16       |
| Electronica/Dance | Journey To Arnhemland                                                                                         | 0.99          | 0.16       |
| Jazz              | Magnetic Ocean                                                                                                | 0.99          | 0.16       |
| Jazz              | Jeru                                                                                                          | 0.99          | 0.16       |
| Classical         | Symphony No. 41 in C Major, K. 551, "Jupiter": IV. Molto allegro                                              | 0.99          | 0.16       |
| Electronica/Dance | Morning Glory                                                                                                 | 0.99          | 0.16       |
| Bossa Nova        | Samba Em Prelúdio                                                                                             | 0.99          | 0.16       |
| Bossa Nova        | Deixa                                                                                                         | 0.99          | 0.16       |
| Hip Hop/Rap       | One For The Road                                                                                              | 0.99          | 0.16       |
| Pop               | Amy Amy Amy (Outro)                                                                                           | 0.99          | 0.16       |
| Hip Hop/Rap       | Commercial 2                                                                                                  | 0.99          | 0.16       |
| R&B/Soul          | Get Up (I Feel Like Being A) Sex Machine                                                                      | 0.99          | 0.16       |
| Heavy Metal       | Gates Of Tomorrow                                                                                             | 0.99          | 0.16       |
| Pop               | Whatever Gets You Thru the Night                                                                              | 0.99          | 0.16       |
| Reggae            | Soldado Da Paz                                                                                                | 0.99          | 0.16       |
| Soundtrack        | United Colours                                                                                                | 0.99          | 0.16       |
| Alternative       | Say Hello 2 Heaven                                                                                            | 0.99          | 0.16       |
| Classical         | Concerto No.2 in F Major, BWV1047, I. Allegro                                                                 | 0.99          | 0.16       |
| Blues             | Hard To Handle                                                                                                | 0.99          | 0.16       |
| Blues             | Sometimes Salvation                                                                                           | 0.99          | 0.16       |
| Easy Listening    | My Kind Of Town                                                                                               | 0.99          | 0.16       |
| Soundtrack        | Lamento Sertanejo                                                                                             | 0.99          | 0.16       |
| Alternative       | Four Walled World                                                                                             | 0.99          | 0.16       |
| Pop               | TriboTchan                                                                                                    | 0.99          | 0.16       |
| Classical         | Suite for Solo Cello No. 1 in G Major, BWV 1007: I. Prélude                                                   | 0.99          | 0.16       |
| Jazz              | E.S.P.                                                                                                        | 0.99          | 0.16       |
| Blues             | Tightrope                                                                                                     | 0.99          | 0.16       |
| Soundtrack        | Assum Preto                                                                                                   | 0.99          | 0.16       |

Some tracks within the other genres recorded higher individual revenue values. However, this did not change the overall finding that the four leading genres generated more total revenue.

### 9. Number of Tracks in the Four Leading Genres
```sql
SELECT COUNT(t.name)
FROM genre g
JOIN track t
ON g.genre_id=t.genre_id
WHERE g.name IN ('Rock', 'Latin', 'Metal', 'Alternative & Punk');
```
| count |
|-------|
| 2582  |
The four leading genres contain 2,582 tracks, while the other genres contain 921 tracks. This shows that the leading genres make up a larger share of the store's music catalogue, which may help explain their strong revenue contribution.

### 10. Number of Tracks in the Other Genres
```sql
SELECT COUNT(t.name)
FROM genre g
JOIN track t
ON g.genre_id=t.genre_id
WHERE g.name NOT IN ('Rock', 'Latin', 'Metal', 'Alternative & Punk');
```
| count |
|-------|
| 921   |
The other genres contain 921 tracks, compared with 2,582 tracks in the four leading genres. This shows that fewer tracks are available across the other genres.









