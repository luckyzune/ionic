## 在每个ionic项目Dockerfile里加上以下代码

```
# Install app dependencies, using wildcard if package-lock exists
COPY package.json /app
COPY package-lock.json /app

# install dependencies
RUN npm ci

# Bundle app source
COPY . /app

# set to production
RUN export NODE_ENV=production

# build
RUN npm run build
```