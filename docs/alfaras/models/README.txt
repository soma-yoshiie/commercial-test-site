【3Dモデル（GLB）の置き場所】

宿泊券詳細ページの3Dビューアで表示するモデル（.glb 形式）をこのフォルダに置きます。

■ 全物件で同じモデルを使う場合
  1) このフォルダ（docs/alfaras/models/）に GLB ファイルを置く
       例： docs/alfaras/models/villa.glb
  2) docs/alfaras/index.html の中ほどにある
       const DEFAULT_MODEL_URL = '...';
     を次のように書き換える
       const DEFAULT_MODEL_URL = 'models/villa.glb';

■ 物件ごとに別のモデルを使う場合
  index.html 内の LISTINGS 配列で、対象物件に model を追加する
       { id:12, cat:'villa', title:'...', ..., model:'models/villa-12.glb' }

■ 補足
  ・初期状態では、確認用に外部CDNのサンプルGLBを読み込みます。
  ・GLBが見つからない／読み込みに失敗した場合は、自動で簡易プレースホルダ
    （ヴィラ風の3D）を表示するので、画面が真っ白になることはありません。
  ・glTF(.gltf + .bin + テクスチャ)よりも、1ファイルにまとまった .glb 形式を推奨します。
  ・スマホ表示も考慮し、なるべく軽量（数MB以内・テクスチャ2K程度）のモデルが快適です。
