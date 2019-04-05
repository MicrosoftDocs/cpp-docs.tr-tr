---
title: Derleyici Hatası C3467
ms.date: 11/04/2016
f1_keywords:
- C3467
helpviewer_keywords:
- C3467
ms.assetid: e2b844d0-4920-412f-99fd-cd8051c4aa41
ms.openlocfilehash: 70375950543b9525fca10fff3084c923095fa35e
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58780762"
---
# <a name="compiler-error-c3467"></a>Derleyici Hatası C3467

'type': Bu tür zaten iletilmiş

Derleyici, aynı türde birden fazla ileriye doğru türü bildirimi bulunamadı. Tür başına yalnızca bir bildirimine izin verilir.

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir bileşen oluşturur.

```
// C3467.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3467 oluşturur.

```
// C3467_b.cpp
// compile with: /clr /c
#using "C3467.dll"
[ assembly:TypeForwardedTo(R::typeid) ];
[ assembly:TypeForwardedTo(R::typeid) ];   // C3467
```