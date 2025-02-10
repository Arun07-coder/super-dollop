version: "3"
services:
  s3:
    image: "minio/minio"
    hostname: "storage"
    restart: "no"
    volumes:
      - data:/data
    ports:
      - "9000:9000"
      - "9001:9001"
    entrypoint: ["minio", "server", "/data","--console-address",":9001"]
    networks:
      - local
volumes:
  data:
networks:
  local:

# super-dollop
