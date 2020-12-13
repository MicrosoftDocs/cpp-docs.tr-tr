---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2272'
title: Derleyici hatası C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 5a46c68a09eaec9fc33ef4eaa64afaebea411659
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336246"
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
