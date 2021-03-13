![image](https://user-images.githubusercontent.com/19686958/111029182-2e9be080-8436-11eb-9008-322213fc7e28.png)


做如下修改可以构建出APPLE ARM版的应用，达到基本可用的程度
1. 删除package-lock.json
2. 修改package.json
   ```
   "electron": "^11.3.0",
   "electron-builder": "^22.9.1",
   ```
3. 安装依赖`yarn`或`npm install`(该步骤需要有稳定良好的网络环境)
4. 修改`pack/electron/package.json`
   ```
   "electronVersion": "11.3.0",
   // 以及build, mac下的
   // target: [
   //   "dmg", "mas"
   // ],  
   // 为
   "target": {
     "target": "dir",
     "arch": [
       "arm64"
     ]
   },
   ```
5. 构建`yarn pack:prepare`或`npm run pack:prepare`
6. 继续构建`yarn pack:mac`或`npm run pack:mac`

也可以：
1. 下载当前代码
3. 安装依赖`yarn`或`npm install`(该步骤需要有稳定良好的网络环境)
5. 构建`yarn pack:prepare`或`npm run pack:prepare`
6. 继续构建`yarn pack:mac`或`npm run pack:mac`


### 最终生成的文件位于dist/build-apps/mac-arm64
