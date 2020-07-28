---
title: Derleyici hatası C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: e4163d68e0fbfea062279ba91e2c902855245e4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220398"
---
# <a name="compiler-error-c2272"></a>Derleyici hatası C2272

' function ': statik üye işlevlerde değiştiricilere izin verilmez

Bir **`static`** üye işlevi, [const](../../cpp/const-cpp.md) veya [volatile](../../cpp/volatile-cpp.md)gibi bir bellek modeli belirticisi ile tanımlanır ve bu tür değiştiricilere **`static`** üye işlevlerinde izin verilmez.

Aşağıdaki örnek C2272 oluşturur:

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
