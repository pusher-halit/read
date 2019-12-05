    version: "2"
    services:
    node:
        image: "node:latest"
        user: "node"
        working_dir: /home/app/prod/fatura2
        volumes:
        - ./:/home/app/prod/fatura2
        expose:
        - "8080"
        ports:
        - "8080:8080"
        command: "npm run s"
    json-server:
        image: vimagick/json-server
        command: -H 0.0.0.0 -p 3000 -w ./src/api/index.json
        ports:
        - "3000:3000"
        working_dir: /home/app/prod/fatura2
        volumes:
        - ./:/home/app/prod/fatura2
        restart: always