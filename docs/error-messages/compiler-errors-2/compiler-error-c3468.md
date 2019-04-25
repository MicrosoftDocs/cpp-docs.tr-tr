---
title: Derleyici Hatası C3468
ms.date: 11/04/2016
f1_keywords:
- C3468
helpviewer_keywords:
- C3468
ms.assetid: cfd320db-2f6e-4e0d-ba02-e79ece87e1e0
ms.openlocfilehash: e3870fa21e2b4a932937edd49091980406a5ff0d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62173190"
---
# <a name="compiler-error-c3468"></a>Derleyici Hatası C3468

'type': bir tür yalnızca bir derlemeye iletebilirsiniz:

'`file`' bir derleme değil

Yalnızca bir bütünleştirilmiş kodundaki türler iletilebilir.

Daha fazla bilgi için [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

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