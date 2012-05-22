GoogleRefine:

Aby zastąpić jakieś znaki możemy użyć takiej komendy: (tutaj z wyrażeniem regularnym (java regex)

    value.replace(/[\Q[]\E]/, ",")
    
Ogólna postać to:
    
    value.replace(string, string)
  
  
Operacje typu if, podobne do excela
    
    if(test, wartość_jeżeli_prawda, wartość_jeżeli_nieprawda)
	
	

Przykład z freebasem:)

używamy freebase'a, jak już poprawimy

    klikamy add columns from Freebase

Można użyć fetchurl'a i ściagnąć sobie jsony:)
	  
    klikamy add columns by fetching URLs
    
Tutaj skorzystamy z imdbapi.com
    
    'http://www.imdbapi.com/?t='+value.replace(" ", "+")

Możemy obsługiwać jsona poprzez parseJson
	
    parseJson(value)["Runtime"]
	  
    parseJson(value)["Plot"]
	
Możemy to wyeksportwać do jsona, albo do MySQL'a:

    INSERT INTO sheakspearAdaptations (0,{{jsonize(cells["Title"].value)}},{{jsonize(cells["Adaptations"].value)}},{{jsonize(cells["Runtime"].value)}},{{jsonize(cells["Plot"].value)}},{{jsonize(cells["Directed by"].value)}})
    
A nawet do innych formatów, np: kodowanie wikipedii.