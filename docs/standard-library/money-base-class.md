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
ms.openlocfilehash: 3195d2c988abcfb2d62acb4ece957c8c5156bbd7
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38965694"
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
