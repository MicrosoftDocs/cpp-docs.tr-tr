---
title: Derleyici Uyarısı (düzey 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: dfc3a91b2dcb3ed1e8f4f4993edd67219a6bf1d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163851"
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

ardından,

```cpp
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```
