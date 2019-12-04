---
title: Derleyici hatası C2531
ms.date: 11/04/2016
f1_keywords:
- C2531
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
ms.openlocfilehash: 4247e026f6680adab45ceebe2b395ad781ccfc7e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737120"
---
# <a name="compiler-error-c2531"></a>Derleyici hatası C2531

' tanımlayıcı ': bir bit alanına yönelik başvuru geçersiz

Bit alanlarına başvurulara izin verilmiyor.

Aşağıdaki örnek C2531 oluşturur:

```cpp
// C2531.cpp
// compile with: /c
class P {
   int &b1 : 10;   // C2531
   int b2 : 10;   // OK
};
```
