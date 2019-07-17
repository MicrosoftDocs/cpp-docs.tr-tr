---
title: '&lt;sınırları&gt; sabit listeleri'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68245351"
---
# <a name="ltlimitsgt-enums"></a>&lt;sınırları&gt; sabit listeleri

## <a name="float_denorm_style"></a> float_denorm_style

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

## <a name="float_round_style"></a> float_round_style

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
