君津周辺 防災・地形Webマップ用データ

【Web用の形式】
・CS立体図: XYZ WebP タイル  tiles/cs/{z}/{x}/{y}.webp
  minZoom=10 / maxNativeZoom=17 / maxZoom=19（17より上はオーバーズーム）
・ベクター: GeoJSON / EPSG:4326
・index.html: Leaflet 1.9.4 用のサンプル。地理院タイルを背景に表示します。

【CS立体図】
国土地理院 DEM1A（航空レーザ、1m）4メッシュを使用。
元DEMは JGD2024 / 平面直角座標系IX系で計算し、表示用タイルだけWeb Mercator XYZに変換しています。
曲率・傾斜の計算は1mグリッド上で実施しています。
色調はFME版マニュアル系に近いパレットを参考にしたCS表現です。
設定: 標高0-400m、傾斜0-1.047rad(約60度)、曲率-0.1～0.1、Gaussian sigma=3 / radius=6px。

【収録ベクター】
・evacuation.geojson          指定緊急避難場所等（添付 12000_2）
・bus_stops.geojson           バス停留所（P11）
・sabo_designated.geojson     砂防指定地（A52）
・landslide_prevention.geojson 地すべり防止区域（A46）
・steep_slope_danger.geojson  急傾斜地崩壊危険区域（A47）
・embankment_regulation.geojson 盛土規制区域（A56）
・historical_admin.geojson    旧行政区域（N03。現行行政界ではないので参考表示）

ベクターはDEMの表示範囲にクリップし、Web表示用に軽量化しています。
法定区域データは国土数値情報の位置確認用データで、法定図書そのものではありません。

【使い方】
フォルダ構成を崩さずWebサーバへ置き、index.htmlを開いてください。
file:// で直接開くとブラウザの制約でGeoJSONのfetchが失敗する場合があります。
GitHub Pages / Netlify / 通常のWebサーバならそのまま動きます。

【Blogger】
Blogger本文へ9,000個以上のタイルを直接置く方式ではなく、GitHub Pages等へこのフォルダを置き、
Bloggerからiframeやリンクで表示する構成が扱いやすいです。
