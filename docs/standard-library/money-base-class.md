---
description: 'Hakkında daha fazla bilgi edinin: money_base sınıfı'
title: money_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: 295984cfed4d6fdd47c772e29765c1484f52d32a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230477"
---
# <a name="money_base-class"></a>money_base Sınıfı

Sınıfı, [moneypunct](../standard-library/moneypunct-class.md)sınıf şablonunun tüm uzmanlıklarıyla ortak bir numaralandırma ve bir yapı tanımlar.

## <a name="syntax"></a>Syntax

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Açıklamalar

Sabit listesi `part` Yapı deseninin dizi alanının öğelerinde olası değerleri açıklar. Değerleri `part` şunlardır:

- `none` sıfır veya daha fazla boşluğu eşleştirmek veya hiçbir şey oluşturmak için.

- `sign` pozitif veya negatif bir işareti eşlemek veya oluşturmak için.

- `space` sıfır veya daha fazla boşluğu eşleştirmek veya bir boşluk oluşturmak için.

- `symbol` bir para birimi sembolünü eşleştirmek veya oluşturmak için.

- `value` bir parasal değeri eşleştirmek veya oluşturmak için.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
