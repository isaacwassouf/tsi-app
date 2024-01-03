# Typing Speed Improvement

This is the final submission for the **Project Software Engineering** course.

# Structure
This project is structured with three repositories
- The **PWA** repository.
- The **API** repository.
- The **DevOps** repository.

# Installation
In order to install the project successfully please follow the following steps.

## PWA
Create the ```.env``` file for the PWA
```bash
cd ./tsi-pwa && cp .env.example .env
```

## API
Create the ```.env``` file for the API
```bash
cd ./tsi-api && cp .env.example .env
```

## DevOps
- Create the ```proxy``` docker network by running the following command
	```bash
	docker network create "proxy"
	```

- Add the following host entries to the ```/etc/hosts``` file:
	```bash
	127.0.0.1  app.pwa-tsi.local
	127.0.0.1  app.api-tsi.local
	127.0.0.1  app.dicebear-tsi.local
	```


# Running the application
-	Navigate to the ```tsi-devops``` repository 
	```bash
	cd ./tsi-devops
	```
- Build and run the containers with Docker Compose
	```bash
	docker compose up --build
	```
- After the containers start running, attach a shell to the api container
	```bash
	docker exec -it tsi_api /bin/sh
	```
- Ensure that the cache is cleared by running the following command
	```bash
	make clear-cache
	```
- Run the database migrations
	```bash
	make migrate
	```