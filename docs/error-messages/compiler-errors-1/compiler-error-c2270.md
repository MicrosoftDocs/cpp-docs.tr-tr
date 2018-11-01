---
title: Derleyici Hatası C2270
ms.date: 11/04/2016
f1_keywords:
- C2270
helpviewer_keywords:
- C2270
ms.assetid: b52c068e-0b61-42e7-b775-4d57b3ddcba0
ms.openlocfilehash: 704d397f06432575b7db531039b4454d4716c54e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50432001"
---
# <a name="compiler-error-c2270"></a>Derleyici Hatası C2270

'function': üye olmayan işlevlerde değiştiricilere izin verilmez

İle bildirilen bir değiştiricilere işlevi [const](../../cpp/const-cpp.md), [geçici](../../cpp/volatile-cpp.md), veya başka bir bellek modeli değiştiricisi.

Aşağıdaki örnek, C2270 oluşturur:

```
// C2270.cpp
// compile with: /c
void func1(void) const;   // C2270, nonmember function

void func2(void);

class CMyClass {
public:
   void func2(void) const;
};
```