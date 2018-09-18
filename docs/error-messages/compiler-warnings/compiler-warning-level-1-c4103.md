---
title: Derleyici Uyarısı (düzey 1) C4103 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4103
dev_langs:
- C++
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1942acc2d9c5c274806e06127f9f98d4bfcb5077
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085543"
---
# <a name="compiler-warning-level-1-c4103"></a>Derleyici Uyarısı (düzey 1) C4103

'filename': #pragma pack(pop) eksik olduğundan üst bilgi eklendikten sonra değiştirilen hizalama olabilir

Paketleme sınıfların düzenini etkiler ve sık, üstbilgi dosyaları arasında değişiklikleri paketleme, olabilir sorunları.

#Pragma kullanın [paketi](../../preprocessor/pack.md)bu uyarıyı çözmek için üst bilgi dosyasını çıkmadan önce (pop).

Aşağıdaki örnek, C4103 oluşturur:

```
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

Ardından,

```
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```