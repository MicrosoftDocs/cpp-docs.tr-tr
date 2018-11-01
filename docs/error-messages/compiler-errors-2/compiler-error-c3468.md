---
title: Derleyici Hatası C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: 185bd35bb732f592c75912fe69d4491252fe9d0b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476121"
---
# <a name="compiler-error-c3468"></a>Derleyici Hatası C3468

'type': bir tür yalnızca bir derlemeye iletebilirsiniz:

'`file`' bir derleme değil

Yalnızca bir bütünleştirilmiş kodundaki türler iletilebilir.

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir modül oluşturur.

```
// C3468.cpp
// compile with: /LN /clr
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3468 oluşturur.

```
// C3468_b.cpp
// compile with: /clr /c
#using "C3468.netmodule"
[ assembly:TypeForwardedTo(R::typeid) ];   // C3468
```