---
title: money_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: c614832b0cbb1cc23e42ecb3a939ccf1334a5cea
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689318"
---
# <a name="money_base-class"></a>money_base Sınıfı

Sınıfı, [moneypunct](../standard-library/moneypunct-class.md)sınıf şablonunun tüm uzmanlıklarıyla ortak bir numaralandırma ve bir yapı tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Açıklamalar

Sabit Listesi `part` yapı deseninin dizi alanının öğelerinde olası değerleri açıklar. @No__t_0 değerleri şunlardır:

- sıfır veya daha fazla boşlukla eşleşecek veya hiçbir şey oluşturmaya `none`.

- `sign` pozitif veya negatif bir işaret ile eşleşecek veya oluşturulacak.

- sıfır veya daha fazla boşlukla eşleşecek veya bir boşluk oluşturacak `space`.

- bir para birimi simgesi eşleştirmek veya oluşturmak için `symbol`.

- bir parasal değer eşlemek veya oluşturmak için `value`.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
