---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3467'
title: Derleyici hatası C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: c00c78852380537d744c8d01681a921e487826df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113447"
---
# <a name="compiler-error-c3467"></a>Derleyici hatası C3467

' Type ': Bu tür zaten iletilmiş

Derleyici aynı tür için birden fazla ileri tür bildirimi buldu. Tür başına yalnızca bir bildirime izin verilir.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

Aşağıdaki örnek C3467 oluşturur.

```cpp
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```
