# README

) Niveau facile

    Quel est le nombre total d'objets Album contenus dans la base (sans regarder les id bien sûr) ? Album.count(:all) >>> 347
    Qui est l'auteur de la chanson "White Room" ? Track.find_by(title: "White Room").artist >>> Eric clapton
    Quelle chanson dure exactement 188133 milliseconds ? Track.find_by(duration: 188133).title >>> perfect
    Quel groupe a sorti l'album "Use Your Illusion II" ? Album.find_by(title: "Use Your Illusion II").artist >>>> Gun's n roses
 

b) Niveau Moyen

    Combien y a t'il d'albums dont le titre contient "Great" ? (indice) Album.where("title like ?", "%Great%").count >>> 13
    Supprime tous les albums dont le nom contient "music". Album.where("title like ?", "%music%").destroy_all  >>> new count = 343
    Combien y a t'il d'albums écrits par AC/DC ? Album.where(artist: "AC/DC").count >>> 2
    Combien de chanson durent exactement 158589 millisecondes ?  Track.where(duration: 158589).count >>> 0

c) Niveau Difficile

Pour ces questions, tu vas devoir effectuer des boucles dans la console Rails. C'est peu commun mais c'est faisable, tout comme dans IRB.

    puts en console tous les titres de AC/DC. 2.5.1 :052 > Track.where(artist: "AC/DC").each do |i|
                                                                 puts i.title
                                                                   end

    puts en console tous les titres de l'album "Let There Be Rock". Track.where(album: "Let There Be Rock").each do |i|
                                                                          puts i.title
                                                                          end

    Calcule le prix total de cet album ainsi que sa durée totale.

price = 0
duration = 0

    Track.where(album: "Let There Be Rock").each do |i| 
    puts price += i.price
   puts duration += i.duration
   end

price = 7.920000000000001 $
duration = 2453259 ms


    Calcule le coût de l'intégralité de la discographie de "Deep Purple". >>>> 90.0899999999999
price = 0
 Track.where(artist: "Deep Purple").each do |i|
   puts price += i.price
   end



    Modifie (via une boucle) tous les titres de "Eric Clapton" afin qu'ils soient affichés avec "Britney Spears" en artist.

  Track.where(artist: "Eric Clapton").each do |i|
   i.update(artist: "Britney Spears")
   end



