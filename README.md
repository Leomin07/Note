# Note
Eslint + prettier
..prettierrc

```
yarn add prettier eslint-plugin-prettier eslint-config-prettier -D
```

file .eslintrc

```
{
  "extends": ["react-app", "prettier"],
  "plugins": ["react", "prettier"],
  "rules": {
    "prettier/prettier": [
      "warn",
      {
        "singleQuote": true,
        "arrowParens": "avoid",
        "tabWidth": 2,
        "trailingComma": "es5",
        "printWidth": 120,
        "semi": true,
        "jsxSingleQuote": false,
        "endOfLine": "lf"
      }
    ]
  }
}

```

package.json

```
  "lint": "eslint --ext ts,tsx src/",
  "lint:fix": "eslint --fix --ext ts,tsx src/",
  "prettier": "prettier --check \"src/**/(**.tsx|*.ts|*.scss|*.css)\"",
  "prettier:fix": "prettier --write \"src/**/(**.tsx|*.ts|*.scss|*.css)\""
```

.prettierrc
```
{
  "singleQuote": true,
  "arrowParens": "avoid",
  "tabWidth": 2,
  "trailingComma": "es5",
  "printWidth": 120,
  "semi": true,
  "jsxSingleQuote": false,
  "endOfLine": "lf"
}
```
Cách sửa khi bị lỗi
Error while loading rule 'prettier/prettier': context.getPhysicalFilename is not a function
Lỗi này xảy ra do ESLint của Create React App đang dùng phiên bản thấp hơn phiên bản mà eslint-plugin-prettier yêu cầu, vì thế chúng ta cần update ESLint của CRA bằng cách chạy:
yarn upgrade -R eslint
Nếu phiên bản yarn của bạn là 2+ thì chạy
yarn up -R eslint
