## Part 1
Provide one or more Active Record queries that retrieve the requested data for each of the following:

1. Find the albums recorded by the artist Queen.
  ```

  ```
2. Count how many tracks belong to the media type "Protected MPEG-4 video file".
  ```

  ```
3. Find the genre with the name "Hip Hop/Rap".
  ```

  ```
4. Count how many tracks belong to the "Hip Hop/Rap" genre
  ```

  ```
5. Find the total amount of time required to listen to all the tracks in the database.
  ```

  ```
6. Find the highest price of any track that has the media type "MPEG audio file".
  ```

  ```
7. Find the name of the most expensive track that has the media type "MPEG audio file".
  ```

  ```
8. Find the 2 oldest artists.
  ```

  ```
9. Find the least expensive track that has the genre "Electronica/Dance".
  ```

  ```
10. Find all "MPEG autio file" tracks in the genre "Electronica/Dance".
  ```

  ```


## Stretch: Querying the Chinook Database using SQL

1. Find the albums recorded by the artist Queen.
  ```
  SELECT * FROM artists WHERE name = 'Queen';
  SELECT * FROM albums WHERE artist_id = 51;
  ```
2. Count how many tracks belong to the media type "Protected MPEG-4 video file".

3. Find the least expensive track that has the genre "Electronica/Dance".

4. Find the all the artists whose names start with A.

5. Find all the tracks that belong to playlist 1.
