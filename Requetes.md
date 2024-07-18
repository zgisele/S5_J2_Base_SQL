<!-- 1) Récupérer tous les albums-->
SELECT * FROM albums;


<!-- 2)Récupérer tous les albums dont le titre contient "Great"-->
SELECT * FROM albums WHERE title LIKE '%Great%';

<!-- 3)Donner le nombre total d'albums contenus dans la base-->
SELECT COUNT(*) FROM albums;

<!-- 4)Supprimer tous les albums dont le nom contient "music"-->
DELETE FROM albums WHERE title LIKE '%music%';

<!-- 5)Récupérer tous les albums écrits par AC/DC-->
SELECT albums.* FROM albums 
JOIN artists ON albums.artist_id = artists.id 
WHERE artists.name = 'AC/DC';

<!-- 6)Récupérer tous les titres des albums de AC/DC-->
SELECT albums.title FROM albums 
JOIN artists ON albums.artist_id = artists.id 
WHERE artists.name = 'AC/DC';

<!-- 7)Récupérer la liste des titres de l'album "Let There Be Rock"-->
SELECT tracks.title FROM tracks 
JOIN albums ON tracks.album_id = albums.id 
WHERE albums.title = 'Let There Be Rock';

<!-- 8)Afficher le prix de cet album ainsi que sa durée totale-->
SELECT albums.price, SUM(tracks.duration) as total_duration FROM albums 
JOIN tracks ON albums.id = tracks.album_id 
WHERE albums.title = 'Let There Be Rock';

<!-- 9)Afficher le coût de l'intégralité de la discographie de "Deep Purple"-->
SELECT SUM(albums.price) FROM albums 
JOIN artists ON albums.artist_id = artists.id 
WHERE artists.name = 'Deep Purple';

<!-- 10)Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables  albums, artists et tracks-->
<!--a) Insérer un nouvel artiste-->
INSERT INTO artists (name) VALUES ('Favorite Artist');

<!--b) Insérer un nouvel album pour cet artiste (utilisons l'id 1 pour l'exemple)-->
INSERT INTO albums (title, artist_id, price) VALUES ('Favorite Album', 1, 9.99);

<!-- c)Insérer des pistes pour cet album (utilisons l'id 1 pour l'album)-->
INSERT INTO tracks (title, album_id, duration) VALUES ('Track 1', 1, 240);
INSERT INTO tracks (title, album_id, duration) VALUES ('Track 2', 1, 300);



