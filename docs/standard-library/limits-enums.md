---
description: 'Daha fazla bilgi edinin &lt; : &gt; numaralandırmaları sınırlar'
title: '&lt;&gt;numaralandırmaları sınırlar'
ms.date: 11/04/2016
f1_keywords:
- limits/std::float_denorm_style
- limits/std::float_round_style
ms.assetid: c86680a2-ba97-4ed9-8c20-a448857d7dc5
ms.openlocfilehash: 115122a4901298018df8809be56a7fc69249d700
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312871"
---
# <a name="ltlimitsgt-enums"></a>&lt;&gt;numaralandırmaları sınırlar

## <a name="float_denorm_style"></a><a name="float_denorm_style"></a> float_denorm_style

Sabit listesi, bir uygulamanın, Normalleştirilmemiş bir kayan nokta değerini temsil etmek için seçebileceğiniz çeşitli yöntemleri açıklar; normalleştirilmiş bir değer olarak temsil etmek için çok küçük:

```cpp
enum float_denorm_style {
    denorm_indeterminate = -1,
    denorm_absent = 0,
    denorm_present = 1    };
```

### <a name="return-value"></a>Dönüş Değeri

Sabit Listesi şunu döndürür:

- `denorm_indeterminate` Uluslararası formların varlığı veya yokluğu, çeviri sırasında saptanamıyor.

- `denorm_absent` denormallanmış formlar yoksa.

- `denorm_present` denormallanmış formlar varsa.

### <a name="example"></a>Örnek

Bu sabit listesinin değerlerine erişilebilen bir örnek için bkz. [numeric_limits:: has_denorm](../standard-library/numeric-limits-class.md#has_denorm) .

## <a name="float_round_style"></a><a name="float_round_style"></a> float_round_style

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

- `round_indeterminate` yuvarlama yöntemi saptanamıyor.

- `round_toward_zero` sıfıra yuvaralıyorsa.

- `round_to_nearest` En yakın tamsayıya yuvarla.

- `round_toward_infinity` sıfırdan uzağa yuvarlandıysanız.

- `round_toward_neg_infinity` daha negatif tam sayıya yuvarlandıysanız.

### <a name="example"></a>Örnek

Bu sabit listesinin değerlerine erişilebilen bir örnek için bkz. [numeric_limits:: round_style](../standard-library/numeric-limits-class.md#round_style) .
