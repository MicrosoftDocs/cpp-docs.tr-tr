---
title: Derleyici hatası C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: bba505b01df8eb1b253fbecb0db93d94ae62d5ac
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756376"
---
# <a name="compiler-error-c3467"></a>Derleyici hatası C3467

' Type ': Bu tür zaten iletilmiş

Derleyici aynı tür için birden fazla ileri tür bildirimi buldu. Tür başına yalnızca bir bildirime izin verilir.

Daha fazla bilgi için bkz. [tür iletmeC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C3467 oluşturur.

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
