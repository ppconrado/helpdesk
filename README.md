# WEB App - React Native - Helpdesk

```
expo init helpdesk --npm
```

## Style

```
https://nativebase.io/
https://docs.nativebase.io/install-expo
```

```
npm install native-base

```

### Icons - SVG Managment

```
expo install react-native-svg
```

### Import SVG

```

https://github.com/kristerkari/react-native-svg-transformer

 npm install --save-dev react-native-svg-transformer


```

### Add follow content(metro.config.js)

```
const { getDefaultConfig } = require("expo/metro-config");

module.exports = (() => {
  const config = getDefaultConfig(__dirname);

  const { transformer, resolver } = config;

  config.transformer = {
    ...transformer,
    babelTransformerPath: require.resolve("react-native-svg-transformer"),
  };
  config.resolver = {
    ...resolver,
    assetExts: resolver.assetExts.filter((ext) => ext !== "svg"),
    sourceExts: [...resolver.sourceExts, "svg"],
  };

  return config;
})();
```

### Using TypeScript: If you are using TypeScript, you need to add this to your declarations.d.ts file (create one if you don't have one already, but don't put in the root folder of your project): C:\dev\ws-nlw\helpdesk\src\@types

```
declare module "*.svg" {
  import React from 'react';
  import { SvgProps } from "react-native-svg";
  const content: React.FC<SvgProps>;
  export default content;
}
```

### Context

```

expo install react-native-safe-area-context

```

### Fonts (Roboto)

```

expo install expo-font @expo-google-fonts/roboto

```
