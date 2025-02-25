---
core_product:
- security
- csm
synonyms:
- ポスチャスコア
- コンプライアンススコア
title: セキュリティポスチャスコア
---

{{< jqmath-vanilla >}}

[Cloud Security Management Misconfigurations][3] において、セキュリティポスチャスコアとは、環境の何パーセントが、Datadog ですぐに使える[クラウド][1]および[インフラストラクチャー][2]関連のアクティブなコンプライアンスルールをすべて満たしているかを表します。

**計算式**:

$${({\text"Pcrictical"/\text"Pcritical + Fcritical"}^2) *8}+{(\text"Phigh"/\text"Phigh + Fhigh") *6}+{(\text"Pmedium"/\text"Pmedium + Fmedium") *3}+{(\text"Plow"/\text"Plow + Flow") *2}+{(\text"Pinfo"/\text"Pinfo + Finfo") *1}$$

- P は合格と評価される所見の数。
- F は不合格と評価される所見の数。

計算式では、所見の重大度と、重大度ごとの所見の合格/不合格数を考慮して重み付けられた比率が使用されます。`scored:true` のタグが設定されたルールと所見のみが、計算に含まれます。

根本的な問題を解決するか、影響を受けるリソースに関して所見を無効にして、所見を修正することで、組織のスコアを改善することができます。

[1]: /ja/security/default_rules/#cat-posture-management-cloud
[2]: /ja/security/default_rules/#cat-posture-management-infra
[3]: /ja/security/misconfigurations/