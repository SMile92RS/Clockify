# Clockify


	Definisana je varijabla unutar kolekcije Clockify API {{baseUrl}} koja oznacava base url.
	Definisana je varijabla unutar kolekcije Clockify API {{apiKey}} kao current value koja oznacava api key.
	Definisana je varijabla unutar kolekcije Clockify API {{workspaceId}} koja oznacava Id jedinog workspace-a koji se koristi u
		vjezbi.

	REQUESTS

	*Get all my workspaces- prikazuje sve worspaces

	*Get all clients- prikazuje sve klijente

	*Add client with random names- dodaje klijenta sa proizvoljnim imenom

	*Add client (with predefined name)- dodavanje klijenta sa "name" : "Zika Pavlovic".
			Kreirani su testovi:
					-Successful POST request. Status code is 201- testira da li jecode status 201
					-Status code name is Created.
					-Client's name is 'Zika Pavlovic'
			Iz response body je neophodno sacuvati id klijenta, jer ce se tim podatkom manipulisati u sledecim requestovima
	
	*Get client via ID- prikazuje odredjenog klijenta, u trenutnom slucaju klijenta kojeg smo maloprije kreirali
			Kreirani su testovi:
					-Status code is 200 - testira status code
					-Status code name is OK
					-Client's name is 'Zika Pavlovic'
					-Client belongs to 'New exercise workspace'- testira da li korisnik Zika PAvlovic 
						pripada workspaceu "New exercise workspace"

	*Update created client- mijenja podatke o kreiranom klijentu "name" : "Pera Peric".
			Kreirani su testovi:
					-Status code is 200 - testira status code
					-Status code name is OK
					-Client name is 'Pera Peric'- testira da li je novo ime klijenta Pera Peric
					-Client belongs to 'New exercise workspace'worskpace

	*Delete created client- brise klijenta
			Kreirani su testovi:
					-Status code is 200 - testira status code
					-Status code name is OK
					-Client 'Pera Peric' is deleted- testira da li se ovaj klijent brise

	*Get deleted client via ID- biranje izbrisanog klijenta pomocu ID
			Kreirani su testovi:
					-Status code is 404- testira da li je status code 404 (TEST PADA jer je status code 400)

	*Add new project- dodaje novi projekat "name": "First Project"
			Kreirani su testovi:
					-Sucessful POST request 201- testira da li je status code 201
					-Status code name is Created
					-Project name is 'First Project'- testira ime projekta
					-Project belongs to 'New exercise workspace' workspace- testira da li projekat pripada
						workspaceu 'New exercise workspace'
	Potrebno sacuvati projectId jer ce kasnije trebati za druge requestove


	*Get your user info- request potreban da se dobije userId

	*Create new client- kreiranje novog klijenta za potrebe njegovog dodavanja u projekat

	*Add client to project- dodavanje novokreiranog klijenta u projekat. dodavanje u request body "name": "My API Project" i
   		"clientId".
			Kreirani su testovi:
					-Status code is 200
					-Successful POST request- testira da li je status code 201 ili 202.
						TEST PADA, jer je test status 200. U api dokumentaciji stoji da je ocekivani response
						code status 201 Created
					-Status code name is Created
					-Project name is 'First Project'- testira ime projekta
					-Project belongs to 'New exercise workspace' workspace- testira da li projekat pripada
						workspaceu 'New exercise workspace'

	*Delete project- brisanje projekta- prikazuje se greska da je nemoguce izbrisati aktivan projekat, te je sledeci korak izmjena
		projekta iz "active" u "archieved"

	*Archive project- arhiviranje projekta. Request body "archived": "true"

	*Delete archieved project- brisanje arhiviranog projekta.
			Kreirani su testovi:
					-Status code is 200

	*Checking for deleted project- pretrazivanje izbrisanog projekta
			Kreirani su testovi:
					-Status code is 404
					-Status code name is Not Found

	*Delete created client- brisanje kreiranog korisnika u svrhu dodavanja korisnika u projekat
				Kreirani su testovi:
					-Status code is 200
					-Status code name is OK

	*Checking for deleted client- provjeravanje da li je stvarno izbrisan klijent. Status code je 400.
