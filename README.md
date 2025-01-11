## Web service gin

Create a http server with gin framework following this [tutorial](https://go.dev/doc/tutorial/web-service-gin)

## Docker
- Build image

```bash
docker build -t $GH_USERNAME/web-service-gin -f deployments/Dockerfile
```
- Run image in local in production mode
```bash
docker run -p 8080:8080 -e GIN_MODE=release --rm --name web-service-gin vramahandry/web-service-gin 
```