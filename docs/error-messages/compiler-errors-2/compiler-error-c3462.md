---
title: Derleyici Hatası C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: 020556be73f0bad8bea6836c9ec0dd0b92dd7f39
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58781373"
---
# <a name="compiler-error-c3462"></a>Derleyici Hatası C3462

'type': yalnızca içeri aktarılmış bir tür iletilebilir

TypeForwardedTo özniteliği başvurulan meta verilerinde bir tür için uygulanması gerekir.

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir bileşen oluşturur.

```
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3462 oluşturur.

```
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```