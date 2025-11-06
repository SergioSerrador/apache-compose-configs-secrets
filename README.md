<img width="825" height="328" alt="Captura de pantalla 2025-11-06 191542" src="https://github.com/user-attachments/assets/744c1482-e052-45b0-a2f2-d8d7ff4fe140" />

Añadimos estas lineas de db con su imagen, env, volumes y secrets
  db:
    image: postgres:16
    environment:
      POSTGRES_DB: ejemplo
      POSTGRES_USER: usuario
      POSTGRES_PASSWORD_FILE: /run/secrets/pg_pass
    volumes:
      - ./db-init:/docker-entrypoint-initdb.d:ro
    secrets:
      - pg_pass
