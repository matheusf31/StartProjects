# React Native

### Início

- CLI (para não usar o expo):

```
$ yarn add react-native-cli

$ react-native init 'nome'

$ npx react-native init 'nome'
```

### Debug

- Reactotron

```
$ yarn add reactotron-react-native
```

- src/config/ReactotronConfig.js:

```
import Reactotron from 'reactotron-react-native';

if(__DEV__) {
	const tron = Reactotron.configure().useReactNative().connect();

	console.tron = tron;

	tron.clear();
}

$ adb reverse tcp:9090 tcp:9090
```

### ESlint & Prettier

```
$ yarn add eslint -D

$ yarn eslint --init:
	> (terceira)
	> (js modules)
	> (react)
	> (remove todas)
	> (airbnb/js)
	> (no / yes)

$ yarn add prettier eslint-config-prettier eslint-plugin-prettier babel-eslint -D
```

- .eslintrc.js

```
module.exports = {
  env: {
    es6: true,
  },
  extends: [
    'plugin:react/recommended',
    'airbnb',
		'prettier',
		'prettier/react'
  ],
  globals: {
    Atomics: 'readonly',
    SharedArrayBuffer: 'readonly',
  },
	parser: 'babel-eslint',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 2018,
    sourceType: 'module',
  },
  plugins: [
    'react',
		'prettier'
  ],
  rules: {
		"prettier/prettier": "error",
    "react/jsx-filename-extension": [
      "warn",
      {
        extensions: [".jsx", ".js"]
      }
    ],
    "import/prefer-default-export": "off"
  },
};
```

- .prettierrc

```
{
  "singleQuote": true,
  "trailingComma": "es5"
}
```

# Estrutua de pastas

```
- src:

	PASTAS:
	- config: plugins, extensões, algo pro ambiente de desenv
	
	- services: configs com serviços (API, mongoDB, Apolo, axios, etc)
	
	- store: dados da aplicação, config do redux
	
	- assets: imagem, logos, bibliotecas de animações, etc
	
  - componnets: componentes que vou utilizar várias vezes na aplicação (componentes globais)
		- Button: index.js & styles.js
		- Background
		
		
  - pages: onde fica as páginas da aplicação
    - Login: index.js & styles.js
  
  - styles: onde fica os estilos comuns
	
	ARQUIVOS:
  - index.js -> Coloco as rotas no index.js
	- routes.js -> definições das rotas
	
	
```