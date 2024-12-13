**KEPERLUAN UNTUK CODING**
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

**PERINTAH UNTUK MENGHAPUS PROJECT JIKA TERJADI ERROR :**
1. Run as Administrator (cmd)
2. rmdir /s /q "D:\ReactNative\AntarLaundry"

**CARA DOWNLOAD & MENJALANKAN PROJECT REACT NATIVE :**
1. Terminal Alt.1 : npx @react-native-community/cli init antarLaundry
   Terminal Alt.2 : npx react-native init AntarLaundry
2. Terminal : npm install
3. Terminal : npx react-native start
4. Terminal : npx react-native run-android

**CARA MENGHAPUS INSTALASI REACT NATIVE :**
Terminal : npm uninstall -g react-native-cli

**Install React Navigation :**
Untuk berpindah dari screen 1 ke screen yang lainnya.
1. Link : https://reactnavigation.org/docs/getting-started#installation
2. Terminal : npm install @react-navigation/native (2 mb)
3. Terminal : npm install react-native-screens react-native-safe-area-context (1 mb)
4. Terminal : npm install @react-navigation/native-stack (1 mb)
5. Link : https://reactnavigation.org/docs/bottom-tab-navigator/
   Terminal : npm install @react-navigation/bottom-tabs (1 mb)
6. Link : https://github.com/software-mansion/react-native-svg
   Terminal : npm install react-native-svg (6 mb)
7. Link : https://github.com/kristerkari/react-native-svg-transformer
   Terminal : npm install --save-dev react-native-svg-transformer (7 mb)
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

**STRUKTUR FOLDER :**
> src
  > components
  > router
  > assets
  > pages

**CARA MENGUBAH .TSX ke .JSX :**
1. Ganti Ekstensi File
   - Ubah semua file dengan ekstensi .tsx menjadi .jsx
   - Jika ada file TypeScript biasa (.ts), ubah menjadi .js.
2. Hapus atau Sesuaikan Tipe TypeScript
   - Dalam setiap file, hapus semua tipe TypeScript (seperti :string, :number, dll.).
   - Hapus semua import terkait TypeScript, seperti import { FC } from 'react' jika tidak digunakan.
3. Perbarui Konfigurasi Babel
   - Buka file babel.config.js.
     module.exports = {
       presets: ['module:metro-react-native-babel-preset'],
     };
4. Hapus TypeScript Dependencies
   - npm uninstall typescript @types/react @types/react-native
5. Perbarui File Konfigurasi
   - rm tsconfig.json
6. Test project :
   - npx react-native run-android
   - npx react-native run-ios

**FONTS :**
Ketika akan mengganti jenis font,
1. Download font
2. Buat folder dan simpan di dalam path project berikut :
   Path : D:\ReactNative\antarLaundry\android\app\src\main\assets\fonts

**SHAWODW :**
Untuk view shadow
https://ethercreative.github.io/react-native-shadow-generator/

**CHANNEL LAIN :**
1. https://chocolatey.org/install
2. Terminal (Powershell)  : Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
3. Terminal (cmd) : choco install -y nodejs-lts microsoft-openjdk17

tsconfig.json
{
  "extends": "@tsconfig/react-native/tsconfig.json"
}


