---
title: money_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 5b19635cf4d2cce58ec50226c463a075cfac5b0f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455561"
---
# <a name="moneybase-class"></a>money_base Sınıfı

Sınıfı, [moneypunct](../standard-library/moneypunct-class.md)şablon sınıfının tüm uzmanlıklarıyla ortak bir numaralandırma ve bir yapı tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Açıklamalar

Sabit listesi `part` yapı deseninin dizi alanının öğelerinde olası değerleri açıklar. Değerleri `part` şunlardır:

- `none`sıfır veya daha fazla boşluğu eşleştirmek veya hiçbir şey oluşturmak için.

- `sign`pozitif veya negatif bir işareti eşlemek veya oluşturmak için.

- `space`sıfır veya daha fazla boşluğu eşleştirmek veya bir boşluk oluşturmak için.

- `symbol`bir para birimi sembolünü eşleştirmek veya oluşturmak için.

- `value`bir parasal değeri eşleştirmek veya oluşturmak için.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
