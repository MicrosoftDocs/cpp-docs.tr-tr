---
title: '&lt;sınırları&gt; numaralandırmalar'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 567e0538f59c40d57f85d652a8919be6e034cf0b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876040"
---
# <a name="ltlimitsgt-enums"></a>&lt;sınırları&gt; numaralandırmalar

## <a name="float_denorm_style"></a>float_denorm_style

Sabit listesi, bir uygulamanın, Normalleştirilmemiş bir kayan nokta değerini temsil etmek için seçebileceğiniz çeşitli yöntemleri açıklar; normalleştirilmiş bir değer olarak temsil etmek için çok küçük:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Dönüş Değeri

Sabit Listesi şunu döndürür:

- `denorm_indeterminate`, uluslararası formların varlığı veya yokluğu, çeviri sırasında saptanamıyor.

- fazla kullanılabilir formlar yoksa `denorm_absent`.

- fazla kullanılabilir formlar varsa `denorm_present`.

### <a name="example"></a>Örnek

Bu sabit listesinin değerlerine erişilebilen bir örnek için bkz. [numeric_limits:: has_denorm](../standard-library/numeric-limits-class.md#has_denorm) .

## <a name="float_round_style"></a>float_round_style

Sabit listesi, bir uygulamanın kayan nokta değerini bir tamsayı değerine yuvarlarken seçebileceği çeşitli yöntemleri açıklar.

```cpp
enum float_round_style {
    round_indeterminate = -1,
    round_toward_zero = 0,
    round_to_nearest = 1,
    round_toward_infinity = 2,
    round_toward_neg_infinity = 3    };
```

### <a name="return-value"></a>Dönüş Değeri

Sabit Listesi şunu döndürür:

- yuvarlama yöntemi belirlenemiyorsa `round_indeterminate`.

- sıfıra yaklaşdıysanız `round_toward_zero`.

- En yakın tamsayıya yuvarla `round_to_nearest`.

- sıfırdan yuvaralıyorsa `round_toward_infinity`.

- daha negatif tamsayıya yuvarlayıp `round_toward_neg_infinity`.

### <a name="example"></a>Örnek

Bu sabit listesinin değerlerine erişilebilen bir örnek için bkz. [numeric_limits:: round_style](../standard-library/numeric-limits-class.md#round_style) .
