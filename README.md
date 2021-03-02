# docker-php-apache
A skeleton template for a dockerized PHP web app with Apache 2, PHP 7.4 and Composer.
Debian-based.

## Requirements

The dockerized app needs the following minimum requirements to be met:

- Docker 20.10.4
- Docker Compose 1.28.4

---

## Customizations

**TIMEZONE**

Open `docker-compose.yml` and change the timezone data. If you want to use the default server
location's timezone, set it to false. Otherwise, change as needed.

[List of Supported Timezones](https://www.php.net/manual/en/timezones.php)

```bash
# Timezone turned on and set
    args:
        set_timezone: "true"
        tz_data: "Asia/Manila"

# Timezone turned off
    args:
        set_timezone: "false"
        tz_data: "America/Chicago"
```

**CONFIGURATION FILE**

If your web app requires specific configuration settings, you can add them in the `php.ini`
file that was provided in this skeleton template.

---

## Usage

In your console, run:

```bash
docker-compose up -d
```

If you made any changes, you need to rebuild it:

```bash
docker-compose up -d --build
```

After a successful build, you should be able to access the **index** page through your
browser via:

- http://localhost
- http://your-local-ip
- http://your-public-ip

If you need to install packages via [Composer](https://getcomposer.org), run:

```bash
docker-compose run --rm web bash

Creating core_web_run ... done

root@6f781583e86a:/var/www/html# composer --version
Composer version 2.0.11 2021-02-24 14:57:23

# Use composer as you normally will and exit when done

root@6f781583e86a:/var/www/html# exit
```