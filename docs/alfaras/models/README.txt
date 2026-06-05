【3Dモデル（GLB）の置き場所】

宿泊券詳細ページの3Dビューアについて。

■ 既定の表示（GLB不要）
  既定では「そのヴィラの写真」をテクスチャに使った3Dの宿泊券カードを表示します。
  （写真はALFARASの各物件カードと同じものを自動使用するので、設定は不要です）

■ 本格的な3Dモデル（.glb）を使いたい場合
  ・全物件で同じモデル：
      1) このフォルダ（docs/alfaras/models/）に GLB を置く（例：villa.glb）
      2) index.html 内の  const DEFAULT_MODEL_URL = '';  を
         const DEFAULT_MODEL_URL = 'models/villa.glb';  に変更
  ・物件ごとに変える：
      index.html 内の LISTINGS で対象物件に model を追加
        { id:12, cat:'villa', title:'...', ..., model:'models/villa-12.glb' }

■ フォールバック
  GLBの読込に失敗した場合 → 写真カード → 簡易プレースホルダ（ヴィラ風3D）
  の順に自動で切り替わるため、画面が真っ白になることはありません。

■ 補足
  ・glTF(.gltf+.bin+テクスチャ)より、1ファイルにまとまった .glb 形式を推奨。
  ・スマホ表示も考慮し、数MB以内・テクスチャ2K程度の軽量モデルが快適です。
