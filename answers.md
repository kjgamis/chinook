## Part 1
Provide one or more Active Record queries that retrieve the requested data for each of the following:

1. Find the albums recorded by the artist Queen.
  ```
  Artist.where("name = ?", 'Queen')
  Album.where("artist_id = ?", 51)

  OR

  Album.where("artist_id = ?", Artist.where("name = ?", 'Queen').ids)
  ```
2. Count how many tracks belong to the media type "Protected MPEG-4 video file".
  ```
  MediaType.all
  Track.where("media_type_id = ?", 3).count
  ```
3. Find the genre with the name "Hip Hop/Rap".
  ```
   Genre.all.where("name = ?", 'Hip Hop/Rap')
  ```
4. Count how many tracks belong to the "Hip Hop/Rap" genre
  ```
  Genre.all.where("name = ?", 'Hip Hop/Rap').count
  ```
5. Find the total amount of time required to listen to all the tracks in the database.
  ```
  Track.sum('milliseconds')
  ```
6. Find the highest price of any track that has the media type "MPEG audio file".
  ```
  Track.where("media_type_id = ?", MediaType.where("name = ?", "MPEG audio file").ids).maximum(:unit_price)
  ```
7. Find the name of the most expensive track that has the media type "MPEG audio file".
  ```
  Track.where(unit_price: Track.where(media_type_id: MediaType.where('name = ?', 'MPEG audio file').ids).maximum(:unit_price)).pluck(:name)
  ```
8. Find the 2 oldest artists.
  ```
  Artist.order(created_at: :DESC).last(2)
  ```
9. Find the least expensive track that has the genre "Electronica/Dance".
  ```
  Track.where(genre_id: Genre.where('name = ?', 'Electronica/Dance').ids).minimum(:unit_price)
  ```
10. Find all "MPEG audio file" tracks in the genre "Electronica/Dance".
  ```
  Genre.where('name = ?', 'Electronica/Dance').ids
  MediaType.where('name = ?', 'MPEG audio file').ids

  Track.where(genre_id: Genre.where('name = ?', 'Electronica/Dance').ids, media_type_id: MediaType.where('name = ?', 'MPEG audio file').ids).pluck(:name)
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
