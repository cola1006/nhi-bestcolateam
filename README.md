# 全民健保支付標準查碼系統 · nhi.bestcolateam.com

獨立部署的健保碼查詢工具，可樂空軍團隊。資料源自 fund-calculator 主站，由 GitHub Actions 每日自動同步。

## 結構

```
nhi-站/
├─ index.html              # 單頁應用
├─ data/health-codes.json  # 4943 筆健保代碼（自動同步自 fund-calc）
├─ _headers                # CF Pages 安全/快取設定
├─ robots.txt
├─ sitemap.xml
├─ og-image.png            # 1200x630 分享預覽圖（待補）
└─ .github/workflows/
   └─ sync-health-codes.yml  # 每日 UTC 02:00 自動同步資料
```

## 部署

CF Pages → GitHub repo 自動部署。每次推送即自動上線。

## 資料同步

GitHub Actions 每日 UTC 02:00（台灣時間 10:00）從 `https://fund-calculator.pages.dev/data/health-codes.json` 拉取最新資料，有變化才提交 commit 觸發重新部署。也可在 Actions 頁面手動觸發 `Sync health-codes.json from fund-calc`。

## 主資料維護

健保代碼資料的編輯流程仍在 fund-calc 主站（`G:\我的雲端硬碟\Claude-workspace\projects\可樂空軍雲端資料庫\`）。本站只是公開行銷版，資料只入不出。
