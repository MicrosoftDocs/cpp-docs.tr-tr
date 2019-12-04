---
title: Derleyici hatası C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: fd6fdecd3a491ce5f068f4d51d413e6767aabe2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758703"
---
# <a name="compiler-error-c2272"></a>Derleyici hatası C2272

' function ': statik üye işlevlerde değiştiricilere izin verilmez

`static` üye işlevi, [const](../../cpp/const-cpp.md) veya [volatile](../../cpp/volatile-cpp.md)gibi bir bellek modeli belirticisi ile tanımlanır ve bu tür değiştiricilere `static` üye işlevlerinde izin verilmez.

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
