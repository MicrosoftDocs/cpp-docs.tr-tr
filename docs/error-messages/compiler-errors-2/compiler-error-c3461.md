---
title: Derleyici hatası C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: d1bf4af63bac2aaee1da4bb98f23c3b15e98c671
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756636"
---
# <a name="compiler-error-c3461"></a>Derleyici hatası C3461

' Type ': yalnızca bir yönetilen tür iletilebilir

Tür iletme yalnızca CLR türlerinde olabilir.  Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md) .

Daha fazla bilgi için bkz. [tür iletmeC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C3461 oluşturur.

```cpp
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```
