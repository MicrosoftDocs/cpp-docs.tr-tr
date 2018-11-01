---
title: Derleyici Hatası C2458
ms.date: 11/04/2016
f1_keywords:
- C2458
helpviewer_keywords:
- C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
ms.openlocfilehash: 8131b259f89c5cacd07d04edbf6c45adaa25b145
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637859"
---
# <a name="compiler-error-c2458"></a>Derleyici Hatası C2458

'identifier': tanım içinde yeniden tanımlama

Sınıfı, yapı, birleşim veya numaralandırma kendi bildiriminde tanımlandı.

Aşağıdaki örnek, C2458 oluşturur:

```
// C2458.cpp
class C {
   enum i { C };   // C2458
};
```