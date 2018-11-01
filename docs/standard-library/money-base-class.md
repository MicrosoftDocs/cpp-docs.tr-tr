---
title: money_base Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_base
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
ms.openlocfilehash: b0c77b523dbe31bc5b07ae3d736441880fe04546
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610459"
---
# <a name="moneybase-class"></a>money_base Sınıfı

Sınıfı bir numaralandırma ve şablon sınıfının tüm uzmanlıkları için ortak bir yapı tanımlar [moneypunct](../standard-library/moneypunct-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Açıklamalar

Numaralandırma `part` öğelerinin yapısı desenin dizi alanının olası değerleri açıklanmaktadır. Değerlerini `part` şunlardır:

- `none` eşleşen sıfır veya daha fazla boşluk veya hiçbir şey oluşturmak için.

- `sign` eşleşen ya da artı veya eksi işareti oluşturmak için.

- `space` eşleşen sıfır veya daha fazla boşluk veya bir alan oluşturmak için.

- `symbol` eşleşen veya bir para birimi sembolü oluşturmak için.

- `value` eşleşen veya parasal bir değeri oluşturmak için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
