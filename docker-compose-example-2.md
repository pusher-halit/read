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