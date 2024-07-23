<!-- 1) Récupérer tous les albums-->
SELECT * FROM albums;


<!-- 2)Récupérer tous les albums dont le titre contient "Great"-->
SELECT * FROM albums WHERE title LIKE '%Great%';

<!-- 3)Donner le nombre total d'albums contenus dans la base-->
SELECT COUNT(*) FROM albums;

<!-- 4)Supprimer tous les albums dont le nom contient "music"-->
DELETE FROM albums WHERE title LIKE '%music%';

<!-- 5)Récupérer tous les albums écrits par AC/DC-->
INSERT INTO tracks (Name, AlbumId, MediaTypeId, GenreId, Composer, Milliseconds, Bytes, UnitPrice)
VALUES ('Nom de la Piste', 1, 1, 1, 'Compositeur', 300000, 1024000, 0.99);


<!-- 6)Récupérer tous les titres des albums de AC/DC-->
SELECT albums.Title FROM albums JOIN artists ON albums.ArtistId = artists.ArtistId 
WHERE artists.Name = 'AC/DC';

<!-- 7)Récupérer la liste des titres de l'album "Let There Be Rock"-->
SELECT tracks.Name FROM tracks JOIN albums ON tracks.AlbumId = albums.AlbumId WHERE albums.Title = 'Let Ther
e Be Rock';

<!-- 8)Afficher le prix de cet album ainsi que sa durée totale-->
SELECT tracks.UnitPrice, SUM(tracks.Milliseconds) as total_duration FROM albums 
JOIN tracks ON albums.AlbumId = tracks.AlbumId 
WHERE albums.Title = 'Let There Be Rock';

<!-- 9)Afficher le coût de l'intégralité de la discographie de "Deep Purple"-->
SELECT SUM(tracks.UnitPrice) FROM tracks JOIN albums 
JOIN artists ON tracks.AlbumId = albums.AlbumId and albums.ArtistId = Artists.ArtistId
WHERE artists.Name = 'Deep Purple';

<!-- 10)Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables  albums, artists et tracks-->
<!--a) Insérer un nouvel artiste-->
INSERT INTO artists (Name) VALUES ('Favorite Artist');

<!--b) Insérer un nouvel album pour cet artiste (utilisons l'id 1 pour l'exemple)-->
INSERT INTO albums (title, artist_id, price) VALUES ('Favorite Album', 1, 9.99);

<!-- c)Insérer des pistes pour cet album (utilisons l'id 1 pour l'album)-->
INSERT INTO tracks (title, album_id, duration) VALUES ('Track 1', 1, 240);
INSERT INTO tracks (title, album_id, duration) VALUES ('Track 2', 1, 300);



