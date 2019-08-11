# verdaccio nginx dokcer

## Setup with docker-compose

```bash
docker-compose up --build -d
```

### Web UI

```bash
http://localhost:4873 or <your-ip>
```

### Basic Usage

```bash
# Configuring your registry settings as an npm registry
npm config set registry http://localhost:4873 or <your-ip>
```

```bash
# Logging in to an npm registry
npm login --registry=http://localhost:4873 or <your-ip>
```

```bash
# Publish a package
npm publish --registry=http://localhost:4873 or <your-ip>
```

```bash
# Remove a package
npm unpublish --registry http://localhost:4873 or <your-ip>
```

```bash
# Install a package
npm install --registry=http://localhost:4873 or <your-ip>
```

User already

 ```bash
 user: admin
 pass: admin!
```

There are some tools you can create a new user for htpasswd
[Generator htpasswd](http://www.htaccesstools.com/htpasswd-generator/)
open verdaccio/htpasswd file, add a new line and paste that what the tool is created

#### Note* If your 404 no such package available error

If your using docker then the following worked for me:

```bash
docker-compose exec --user root verdaccio /bin/sh
```

and than

```bash
chown verdaccio: /verdaccio/ -R
```
