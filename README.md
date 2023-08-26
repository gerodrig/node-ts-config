# Steps to Use Node with TypeScript
More Information - [Official Docs](https://nodejs.dev/en/learn/nodejs-with-typescript/)

1. Install TypeScript and Node types as a development dependency
```
npm i -D typescript @types/node
```
2. Initialize the TypeScript configuration file (Can be configured to your liking)
```
npx tsc --init --outDir dist/ --rootDir src
```

3. **Optional** - To transpile the code, you can use this command
```
npx tsc
npx tsc --watch
```

4. Configure Nodemon and Node-TS
```
npm install -D ts-node nodemon
```
5. Create a Nodemon configuration file - **nodemon.json**
```
{
  "watch": ["src"],
  "ext": ".ts,.js",
  "ignore": [],
  "exec": "npx ts-node ./src/app.ts"
}
```
6. Create a script to run in development in the **package.json**
```
  "dev": "nodemon"
  "dev": "npx nodemon" // En caso de no querer instalar nodemon
```

7. Install rimraf (Tool that works similar to rm -f) to remove directories
```
npm install -D rimraf
```

8. Create scripts in the package.json for building and starting in production
```
   "build": "rimraf ./dist && tsc",
   "start": "npm run build && node dist/app.js"
```


