# アルゴリズム

各種条件を考慮して、割付条件の **厳しい** コマ（科目別）から割付を行う  
割付出来ないコマが発生した時点で、差し替え可能なコマの科目を検索し  
該当コマの割付から再度行う

1. コマを生成する  
   生成に必要なマスタデータを揃えて、すべてのコマを生成する
1. 割付優先度の付与  
   手動または自動で設定されたポイント的なものをもとにして  
   科目別に割付の優先度を設定する
1. 割付開始  
   制約をもとにして、割付可能なマスにコマを割付
1. 再割付  
   割付できないコマが発生した場合、１科目戻って再度割付を行う  
   その再、現在割付されているマスをＮＧマスとして記憶し、  
   再割付する際の１種の制約として扱うこととする

# コマが持つ属性

- 作成時点
  - 担当教師(List)
  - 科目
  - 時数
  - 教室
  - 制約
    - ~科目と続いてはいけない
    - ~曜日に実施してはいけない
    - ~時間目に実施してはいけない
- 割付後
  - 割付順
  - 曜日
  - 時間
  - 学年
  - クラス
- 再割付時
  - NG マス(List)
