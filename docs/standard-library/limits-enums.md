---
title: '&lt;sınırları&gt; sabit listeleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 5795d146714c6eb00902518347138a98574679a8
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960654"
---
# <a name="ltlimitsgt-enums"></a>&lt;sınırları&gt; sabit listeleri

|||
|-|-|
|[float_denorm_style](#float_denorm_style)|[float_round_style](#float_round_style)|

## <a name="float_denorm_style"></a>  float_denorm_style numaralandırması

Numaralandırma normalleştirilmişlikten çıkarılmış bir kayan nokta değeri temsil eden bir uygulama seçim yapabileceği çeşitli yöntemleri açıklar; normalleştirilmiş bir değer olarak göstermek için çok küçük bir:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Dönüş Değeri

Sabit listesi döndürür:

- `denorm_indeterminate` varlığı veya yokluğu normalleştirilmişlikten çıkarılmış formlarının çeviri zaman belirlenemiyorsa.

- `denorm_absent` normalleştirilmişlikten çıkarılmış forms yoksa.

- `denorm_present` normalleştirilmişlikten çıkarılmış forms mevcut olması durumunda.

### <a name="example"></a>Örnek

Bkz: [numeric_limits::has_denorm](../standard-library/numeric-limits-class.md#has_denorm) içinde bu sabit listesi değerlerini erişilebilir bir örnek.

## <a name="float_round_style"></a>  float_round_style numaralandırması

Sabit bir kayan nokta değeri tamsayıya yuvarlama uygulaması seçim yapabileceği çeşitli yöntemleri açıklar.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Dönüş Değeri

Sabit listesi döndürür:

- `round_indeterminate` Yuvarlama yöntemi belirlenemiyorsa.

- `round_toward_zero` sıfıra doğru YUVARLA.

- `round_to_nearest` en yakın tamsayıya yuvarlamak.

- `round_toward_infinity` sıfırdan ıraksayarak YUVARLA.

- `round_toward_neg_infinity` Yuvarlak daha negatif tamsayı.

### <a name="example"></a>Örnek

Bkz: [numeric_limits::round_style](../standard-library/numeric-limits-class.md#round_style) içinde bu sabit listesi değerlerini erişilebilir bir örnek.

## <a name="see-also"></a>Ayrıca bkz.

[\<sınırları >](../standard-library/limits.md)<br/>
