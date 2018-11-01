---
title: '&lt;sınırları&gt;'
ms.date: 11/04/2016
f1_keywords:
- limits/std::<limits>
- <limits>
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
ms.openlocfilehash: aa143198ec662ae33263d1ee5d79ffadf51c61d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632459"
---
# <a name="ltlimitsgt"></a>&lt;sınırları&gt;

Şablon sınıfı tanımlar `numeric_limits` ve kayan nokta ifadeleri ilgili ve yuvarlama iki numaralandırma.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <limits>

```

## <a name="remarks"></a>Açıklamalar

Açık uzmanlıkları `numeric_limits` sınıfı temel türlerin karakter, tamsayı ve kayan nokta türleri dahil olmak üzere birçok özelliklerini açıklar ve **bool** giderilen yerine tanımlanan uygulaması olan C++ dilinin kurallar. Özellikleri açıklanan \<sınırları > doğruluğu, minimum ve maksimum dahil yuvarlama ve türü hata sinyali gösterimleri, boyutlandırılmış.

### <a name="enumerations"></a>Numaralandırmalar

|||
|-|-|
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|Numaralandırma normalleştirilmişlikten çıkarılmış bir kayan nokta değeri temsil eden bir uygulama seçim yapabileceği çeşitli yöntemleri açıklar; normalleştirilmiş bir değer olarak göstermek için çok küçük bir:|
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|Sabit bir kayan nokta değeri tamsayıya yuvarlama uygulaması seçim yapabileceği çeşitli yöntemleri açıklar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[numeric_limits Sınıfı](../standard-library/numeric-limits-class.md)|Şablon sınıfı, yerleşik sayısal türler aritmetik özelliklerini açıklar.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
