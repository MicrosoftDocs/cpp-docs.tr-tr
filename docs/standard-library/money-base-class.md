---
title: money_base sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_base
dev_langs:
- C++
helpviewer_keywords:
- money_base class
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 805045e4ea63f153e9a35b0d4b068bd69874b93f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="moneybase-class"></a>money_base Sınıfı

Bir numaralandırma ve Şablon sınıfı tüm özelleştirmeleri için ortak bir yapı sınıf tanımlar [moneypunct](../standard-library/moneypunct-class.md).

## <a name="syntax"></a>Sözdizimi

```cpp
struct pattern
{
   char field[_PATTERN_FIELD_SIZE];
};
```

## <a name="remarks"></a>Açıklamalar

Numaralandırma **bölümü** yapısı düzeninde dizi alanının öğelerinde olası değerleri açıklanmaktadır. Değerlerini **bölümü** şunlardır:

- **Hiçbiri** sıfır veya daha fazla boşluk veya hiçbir şey oluşturmak üzere.

- **oturum** eşleşen veya olumlu veya olumsuz bir oturum oluşturur.

- **alan** sıfır veya daha fazla boşluk veya bir alan oluşturmak üzere.

- **Sembol** veya bir para birimi simgesini oluşturmak üzere.

- **değer** veya parasal bir değer üretmek üzere.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
