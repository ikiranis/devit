# devit

## Docker Dev environment for PHP, npm, Laravel, Vue, etc

Contains

- PHP-FPM
- GD
- Composer
- Xdebug
- Npm/Vue

### Build

- Clone these files in a folder
- Build the docker image

```
docker build . -t devit:1.0
```

- Go to your project folder and run any command you want, after the:

```
docker run --rm --init -t -v $(pwd):/www -w /www -p 8000:8000 devit:1.0
```

Example:

```
docker run --rm --init -t -v $(pwd):/www -w /www -p 8000:8000 devit:1.0 composer install
```


### Use an alias

Edit ~/.bashrc

```
nano ~/.bashrc
```

Add the alias

```
alias devit="docker run --rm --init -t -v $(pwd):/www -w /www -p 8000:8000 devit:1.0"
```

Run to reload bashrc

```
. ~/.bashrc
```

Use the alias to run a command

```
devit composer install
```


