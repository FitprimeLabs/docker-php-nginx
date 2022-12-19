# fitprimelabs/php-nginx

[![Docker Pulls](https://img.shields.io/docker/pulls/fitprimelabs/docker-php-nginx)](https://hub.docker.com/r/fitprimelabs/docker-php-nginx)
[![GitHub Repo](https://img.shields.io/badge/github-repo-yellowgreen)](https://github.com/fitprimelabs/docker-php-nginx)
[![GitHub License](https://img.shields.io/github/license/fitprimelabs/docker-php-nginx)](https://github.com/fitprimelabs/docker-php-nginx/blob/main/LICENSE)

## This projects is forked from https://github.com/fontebasso/docker-php-nginx

This project is container image docker for run PHP with NGINX.

This image is ready to run in production, suggestions for improvements and corrections are very welcome, see [how to contribute](CONTRIBUTING.md).

However, if you identify a security breach, please report it as soon as possible under guidelines outlined in our [security policy](SECURITY.md).

## Getting Started

Use this docker image as a base to run your project, tested on Laravel 8 projects, map your source code to the `/app` directory and build your image as suggested below:

### Step-to-step

#### 1. Your Dockerfile

```Dockerfile
FROM fitprimelabs/php-nginx:[version]
COPY /src /app
RUN chown -R 82:82 /app
```

> **Important note:**
  we run the command chown -R 82:82 /app to change the user and group owning the files to `www-data`, this avoids permissions issues when running your code.

#### 2. Build a image

```ssh
docker build -t your-app:latest .
```

#### 3. Run application

```ssh
docker run -p 8080:80 -t your-app:latest
```
After `run`, open in your browser `http://localhost:8080` and enjoy!

### Prerequisities

To run this image, only the Docker Engine is needed.

* [Linux](https://docs.docker.com/linux/started/)
* [MacOS](https://docs.docker.com/mac/started/)
* [Windows](https://docs.docker.com/windows/started)

#### Volumes

* `/app` - base directory for your application
* `/app/public` - directory exposed to the world

## Built With

* PHP 8.1
* Nginx
* Imagemagick

See [Dockerfile](https://github.com/fitprimelabs/docker-php-nginx/blob/main/Dockerfile) for details of the extensions, libs and configurations.

## Find Us

* [GitHub](https://github.com/fitprimelabs/docker-php-nginx)

## Authors
* **Federico Maiorini** [FitprimeLabs](https://github..com/fitprimelabs)
### Original author
* **Samuel Fontebasso** - [fontebasso](https://github.com/fontebasso)

See also the list of [contributors](https://github.com/fitprimelabs/docker-php-nginx/contributors) who participated in this project.

## License

The MIT License, see the [LICENSE](https://github.com/fitprimelabs/docker-php-nginx/blob/main/LICENSE) file for details.
