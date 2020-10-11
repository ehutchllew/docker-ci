# Docker Commands
### Build Image
`docker build .`
This looks for a `Dockerfile` within the CWD. To use a spcific file, like `Dockerfile.dev` a flag must be added: `-f`
`docker build -f Dockerfile.dev .`

### Run Container
`docker run -it -p 4001:3000 -v /app/node_modules -v $(pwd):/app {DOCKER_IMAGE_ID}`
* `-it` keeps the terminal open
* `-p` maps the input/local port (4001) to the container port (3000). To access the app we would have to go to our localhost:4001 on our end
* `-v` sets up a volume of files. With no `:` it just bookmarks something on the container. With a `:` it creates a ref locally -- essentially overrides. So in this case, since we aren't copying over `node_modules` in our Dockerfile, we need to bookmark the one created on the container so we have access to dependencies when referencing everything else via `-v $(pwd):/app`.

# Docker Compose Commands
