This is a [Laravel](https://laravel.com) running on ***Octane + Swoole*** example project to use with [`gorunn`](https://github.com/parapidcom/gorunn).

## Getting Started

### Add project to the stack

Create file **mylaravel.yaml** with contents :

```bash
name: mylaravel
git_repo: git@github.com:parapidcom/gorunn-example-laravel
type: php
version: "8.3"
endpoint: mylaravel.local.gorunn.io
env_vars: true
start_command: php artisan octane:start --server=swoole --port 80 --host 0.0.0.0 --watch
listen_port: 80
build_commands:
  - composer install
  - php artisan migrate --force
```

Save it in `~/gorunn/projects/`

### Parse the project
```bash
gorunn parse
```

### Build the project
```bash
gorunn build --app myreact
```
### Open it
Open [https://mylaravel.local.gorunn.io](https://mylaravel.local.gorunn.io) with your browser to see the result.

### Exec
You can execute shell commands inside container:
```bash
gorunn terminal --app mylaravel
```
