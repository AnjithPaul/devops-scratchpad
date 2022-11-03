#devOps #docker 

## ARG vs ENV

- `ENV` is for future running containers. Running dockerized apps can access environment variables
- `ARG` is for building images. This value will not be available after image is built. *e.g:* *default port could be different for dev and prod, when building for each environment, we can pass appropriate port as `ARG`*
