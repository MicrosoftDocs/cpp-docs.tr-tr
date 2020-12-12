---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4103'
title: Derleyici Uyarısı (düzey 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 98a9cfbda60ccc938f2cda7803fcdf7e996def9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272233"
---
# <a name="compiler-warning-level-1-c4103"></a>Derleyici Uyarısı (düzey 1) C4103

' filename ': üst bilgi eklendikten sonra hizalama değişti, nedeni eksik #pragma Pack (pop) olabilir

Paketleme, sınıfların yerleşimini etkiler ve genellikle, üst bilgi dosyaları arasında değişiklik yaparken sorun olabilir.

Bu uyarıyı çözmek için üstbilgi dosyasından çıkmadan önce #pragma [Pack](../../preprocessor/pack.md)(pop) kullanın.

Aşağıdaki örnek C4103 oluşturur:

```cpp
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

Ardından,

```cpp
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```
