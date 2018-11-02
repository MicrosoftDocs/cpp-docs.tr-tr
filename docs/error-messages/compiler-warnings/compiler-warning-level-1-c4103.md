---
title: Derleyici Uyarısı (düzey 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 15d7403d461467e33b7e89957821a311179d33a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577820"
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