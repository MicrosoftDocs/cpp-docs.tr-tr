---
title: Derleyici Hatası C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 1a5a1e47a721cb6edd795012cc45943e63708936
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537430"
---
# <a name="compiler-error-c2272"></a>Derleyici Hatası C2272

'function': statik üye işlevlerinde izin verilmez

A `static` üye işlevi bildirilmiş bir bellek-model tanımlayıcısı ile gibi [const](../../cpp/const-cpp.md) veya [geçici](../../cpp/volatile-cpp.md), ve bu tür değiştiricilere izin verilmez `static` üye işlevleri.

Aşağıdaki örnek, C2272 oluşturur:

```
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```