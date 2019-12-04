---
title: Derleyici hatası C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: 75acfa4d702b31052b7113117c71bf66ed9de149
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758248"
---
# <a name="compiler-error-c2640"></a>Derleyici hatası C2640

' tanımlayıcı ': __based değiştiricisi başvuru üzerinde geçersizdir

`__based` değiştiricisi yalnızca işaretçilerde kullanılabilir.

Aşağıdaki örnek C2640 oluşturur:

```cpp
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```
