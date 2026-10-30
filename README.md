Chinook Music Store Analysis

Project Summary

In this project, I used SQL to analyse the Chinook music store database and answer questions about artists, albums, music genres, and track sales. I wanted to understand which genres generate the most revenue and what factors might explain the differences in their sales performance.

Business Questions

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

Dataset

Chinook Database

[Chinook Database](https://github.com/lerocha/chinook-database
)

The Chinook database contains information about a digital music store, including artists, albums, tracks, genres, customers, and sales records.

Tools Used

- PostgreSQL

Key Findings and Insights

1. Revenue by Genre

Rock, Latin, Metal, and Alternative & Punk collectively generate 73.50% of total revenue. Rock contributes the largest share at 35.50%, followed by Latin at 16.41%. Revenue is concentrated among four of the 20 music genres. These genres play a significant role in the store's revenue performance.

2. Quantity Sold by Genre

The four leading genres account for 77.19% of the total quantity sold. This shows that their high sales volume is an important part of their revenue performance and helps explain why they are the top revenue-generating genres.

3. Track Revenue Comparison

Some tracks within the other genres recorded higher individual revenue values of $3.98, compared with $1.99 and $0.98 for tracks within the four leading genres. Despite this, the four leading genres generated more total revenue and sold in higher quantities. This led to a further investigation of the number of tracks available in the top-performing genres compared with the other genres.

4. Track Catalogue

The four leading genres contain 2,582 tracks, representing 73.70% of the available tracks, while the other genres contain 921 tracks, representing 26.30%. This shows that the leading genres make up a larger share of the store's music catalogue, which helps explain their strong revenue contribution.

5. Catalogue Size and Sales Performance

The revenue contribution of the four leading genres (73.50%) closely matches their share of available tracks (73.70%). However, their quantity share (77.19%) is higher. This indicates that their tracks sell in higher quantities per available track than those in the other genres.

Query Results

[Add link to your query screenshots here]
