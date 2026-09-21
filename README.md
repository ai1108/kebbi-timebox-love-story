# 凱比時光寶盒：爺奶戀愛史時光膠囊

> 個人專案。透過 Kebbi 機器人蒐集阿公阿嬤的戀愛故事，經由 MQTT 傳到 Colab，再用 LINE Messaging API 自動推送到家庭 LINE 群組，讓長輩的回憶被家人看見、留存下來。

## 專案流程

摸 Kebbi 頭 -> Kebbi 打招呼 -> 問第一次約會（語音辨識）-> 問電影趣事（語音辨識）-> 組合成 memory_text -> 透過 MQTT 發送到 Topic -> Colab 端訂閱並收到 -> 呼叫 LINE Messaging API -> 推送到家庭 LINE 群組

## 專案內容

- kebbi_timebox_text.ipynb - 精簡版：MQTT 收到爺奶戀愛故事文字後，直接以純文字訊息推送到 LINE 家庭群組
- kebbi_timebox_flex_with_image.ipynb - 完整版：多了 Flask + ngrok 架設的圖片伺服器，搭配 LINE flex message 把故事文字與照片一起排版成卡片推送到 LINE

## 需要的密鑰

程式碼透過 Colab 的 Secrets 功能讀取密鑰（不會寫死在程式碼裡）。使用前請在 Colab 左側 🔑 Secrets 分別新增：

- LINE_CHANNEL_ACCESS_TOKEN
- LINE_GROUP_ID
- NGROK_AUTHTOKEN（僅完整版需要）

## 作者

鍾嬡 (Audrey)
