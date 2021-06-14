# v2board-cht-enahance
增強 v2board 在繁體中文環境下的字體顯示體驗

## 用法
1. 將 `custom.css` 放到 v2board 目錄的 `/public/assets/[user,admin]` 目錄中
2. 將 static 中的 `inter*` 字體檔案 放到 v2board 目錄的 `/public/assets/[user,admin]/static` 目錄中
3. 使用前後分離部署時，還需修改 index.html，在 head 中 `<link rel="stylesheet" href="./umi.css">` 的後方加入 `<link rel="stylesheet" href="./custom.css">`

## 特點
+ 使用 `font-variant-east-asian: traditional` 屬性將 UI 文字繁體化
+ font-family 增加 Microsoft YaHei 做為 Fallback
+ `block-content` 保持原文，避免套餐說明與工單內容因強制轉換而影響辨識
+ 遠程加載 Inter 字體，為不同平台提供一致的英數字顯示

## 說明
+ UI 繁體化僅更改字體顯示，源碼仍是簡體字。此特性需要字體配合，目前僅 macOS / iOS 自帶的字體支持。
+ 由於此特性會將所有一簡對多繁（制製、系係、表錶、后後 ...）的字強制轉成筆劃多的字形（製造、製度 ...），無論原文為簡體或繁體均會受影響，故維持 `block-content` 原文以免錯別字過多。

## 參考
+ [一行CSS实现全站中文简繁转换](https://www.zhangxinxu.com/wordpress/2021/01/css-simplified-traditional-chinese/comment-page-1/)

## 感謝
+ [google-webfonts-helper.herokuapp.com](https://google-webfonts-helper.herokuapp.com/fonts/inter)