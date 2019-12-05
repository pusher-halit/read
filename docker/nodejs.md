## Nodejs docker-compose.yml example -1
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

## Nodejs docker-compose.yml example -2
        version: "2"
        services:
          node:
            image: "node:8"
            user: "node"
            working_dir: /home/app/start/react
            environment:
              - NODE_ENV=production
            volumes:
              - ./:/home/app/start/react
            expose:
              - "3001"
            ports:
            - "3001:3001"
            command: "npm start"
