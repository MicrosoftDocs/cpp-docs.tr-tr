---
title: Derleyici hatası C3469
ms.date: 11/04/2016
f1_keywords:
- C3469
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
ms.openlocfilehash: 546de5a65f6e4c2fd370ba781d01945df2bbfce5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760549"
---
# <a name="compiler-error-c3469"></a>Derleyici hatası C3469

' Type ': genel bir sınıf iletilemez

Genel bir sınıfta tür iletme kullanamazsınız.

Daha fazla bilgi için bkz. [tür iletmeC++(/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3469.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek C3466 oluşturur.

```cpp
// C3469_b.cpp
// compile with: /clr /c
#using "C3469.dll"
[assembly:TypeForwardedTo(GR::typeid)];   // C3469
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
