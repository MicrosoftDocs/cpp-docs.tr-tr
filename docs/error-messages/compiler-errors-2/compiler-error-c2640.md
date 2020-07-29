---
title: Derleyici hatası C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: eb712379ff3ce25a435f4810f5552bc97f635cdd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212689"
---
# <a name="compiler-error-c2640"></a>Derleyici hatası C2640

' tanımlayıcı ': __based değiştiricisi başvuru üzerinde geçersizdir

**`__based`** Değiştirici yalnızca işaretçilerde kullanılabilir.

Aşağıdaki örnek C2640 oluşturur:

```cpp
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```
