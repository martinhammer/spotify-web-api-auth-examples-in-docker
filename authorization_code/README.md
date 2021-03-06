# Dockerized Spotify Accounts Authentication Examples

This is an attempt to run sample code from [Spotify Accounts Authentication Examples](https://github.com/spotify/web-api-auth-examples) inside Docker.

It is a personal toy project, the main objective being for me to learn about Docker.

## Authorization Code Flow - How to run this

1. You need to have Docker installed.
2. You need to have a Spotify account. 
3. Login to [Spotify for Developers](https://developer.spotify.com/) and create a new application.
4. Note down the "Client ID" and "Client Secret" values.
5. Click Edit Settings and enter the "Redirect URI" parameter (http://localhost:8888/callback should work).
6. Edit the Dockerfile and replace the values of CLIENT_ID, CLIENT_SECRET and REDIRECT_URI parameters with the above values.
7. Change directory to whereever you have placed the Dockerfile, and build the Docker image and run, e.g.

```
docker build -t spotify-example-authorization-code .
docker run -d -p 8888:8888 spotify-example-authorization-code
```

8. Navigate to http://localhost:8888 in your web browser, and hopefully the Spotify authentication page will appear.
