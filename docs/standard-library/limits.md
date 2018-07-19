---
title: '&lt;sınırları&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 66f9401bed0a6c9d0b1ffa09a10f98afa258069d
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964762"
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
