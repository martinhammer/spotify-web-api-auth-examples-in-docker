# Dockerized Spotify Accounts Authentication Examples

This is an attempt to run sample code from [Spotify Accounts Authentication Examples](https://github.com/spotify/web-api-auth-examples) inside Docker.

It is a personal toy project, the main objective being for me to learn about Docker.

## Client Credentials - How to run this

**Because of the way this Spotify example is implemented (there is no web server, the response is only logged into console), you won't see anything so there is very little point actually running this.**

1. You need to have Docker installed.
2. You need to have a Spotify account. 
3. Login to [Spotify for Developers](https://developer.spotify.com/) and create a new application.
4. Note down the "Client ID" and "Client Secret" values.
5. Edit the Dockerfile and replace the values of CLIENT_ID and CLIENT_SECRET  parameters with the above values.
6. Edit the Dockerfile and replace the value of SPOTIFY_USER with your Spotify username.
7. Change directory to whereever you have placed the Dockerfile, and build the Docker image and run, e.g.

```
docker build -t spotify-example-client-credentials .
docker run -d -p 8888:8888 spotify-example-client-credentials
```

8. You won't see anything.
