# Nuxt

## Install Node.js

### Install Node.js with nvm

(tutorial)[https://medium.com/@imvinojanv/how-to-install-node-js-and-npm-using-node-version-manager-nvm-143165b16ce1]

### Install nvm

(nvm)[https://github.com/nvm-sh/nvm]

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```

install latest LTS release of Node.js and npm

```bash
nvm install --lts
```

```bash
nvm alias default <version>
```

```bash
nvm use default
```

### Install just Node.js

```bash
sudo apt install nodejs
```

```bash
sudo apt install npm
```

()[https://www.youtube.com/watch?v=IjJxHfWiz9Y&list=PLAyUwmL7et7PyOSd17L3dELHpz-ACHxqz&index=1&t=9s]

```bash
sudo npm cache clean -f
```

```bash
sudo npm install -g n
```

```bash
sudo n stable
```

# Install Node.js packages

```bash
npm install -g firebase-tools
```

# Initialize Nuxt project

(setup nuxt)[https://nuxt.com/docs/getting-started/installation]

```bash
npx nuxi init <name>
```

(setup firebase)[https://firebase.google.com/docs/web/setup]

```bash
npm install firebase
```

(setup tailwind)[https://tailwindcss.nuxtjs.org/getting-started/setup]

```bash
npm install -D @nuxtjs/tailwindcss
```
