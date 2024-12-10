KEPERLUAN UNTUK CODING
================================================================================
Install :
1. Github Desktop
2. Windows Terminal
				
Extensions :
1. Atom One Dark Theme
2. Material Icon Theme
3. Prettier
   Setting :
   File > Preferences > Setting > search (format on save) & Checklist
4. Color Highlight
5. Babel JavaScript
6. ES7 React/Redux/GraphQL/React-Native snippets
7. Excel Viewer
8. npm Intellisense
9. Path Intellisense
10. React Native Tools
11. React-Native/React/Redux snippets for es6/es7
12. Simple React Snippets
13. Image preview
================================================================================
PERINTAH UNTUK MENGHAPUS PROJECT JIKA TERJADI ERROR :
1. Run as Administrator (cmd)
2. rmdir /s /q "D:\ReactNative\AntarLaundry"
================================================================================
CARA DOWNLOAD & MENJALANKAN PROJECT REACT NATIVE :
1. Terminal Alt.1 : npx @react-native-community/cli init AntarLaundry
   Terminal Alt.2 : npx react-native init AntarLaundry
2. Terminal : npm install
3. Terminal : npx react-native start
4. Terminal : npx react-native run-android

Install React Navigation :
Untuk berpindah dari screen 1 ke screen yang lainnya.
1. Link : https://reactnavigation.org/docs/getting-started#installation
2. Terminal : npm install @react-navigation/native
3. Terminal : npm install react-native-screens react-native-safe-area-context
4. Terminal : npm install @react-navigation/native-stack
5. Link : https://reactnavigation.org/docs/bottom-tab-navigator/
   Terminal : npm install @react-navigation/bottom-tabs
6. Link : https://github.com/software-mansion/react-native-svg
   Terminal : npm install react-native-svg
7. Link : https://github.com/kristerkari/react-native-svg-transformer
   Terminal : npm install --save-dev react-native-svg-transformer
8. metro.config.js:
   Replace Code :
   const { getDefaultConfig } = require("expo/metro-config");

   module.exports = (() => {
     const config = getDefaultConfig(__dirname);

     const { transformer, resolver } = config;

     config.transformer = {
       ...transformer,
       babelTransformerPath: require.resolve("react-native-svg-transformer/expo")
     };
     config.resolver = {
       ...resolver,
       assetExts: resolver.assetExts.filter((ext) => ext !== "svg"),
       sourceExts: [...resolver.sourceExts, "svg"]
     };

     return config;
   })();
================================================================================
1. https://chocolatey.org/install
2. Terminal (Powershell)  : Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
3. Terminal (cmd) : choco install -y nodejs-lts microsoft-openjdk17
