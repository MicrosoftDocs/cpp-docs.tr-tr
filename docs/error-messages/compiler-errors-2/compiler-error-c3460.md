---
title: Derleyici Hatası C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: 3a7fe5c6bbb7198f18f5a5cf7cac26add6e6709b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50676700"
---
# <a name="compiler-error-c3460"></a>Derleyici Hatası C3460

'type': yalnızca bir kullanıcı tanımlı bir tür iletilebilir

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../windows/type-forwarding-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, bir bileşen oluşturur.

```
// C3460.cpp
// compile with: /LD /clr
public ref class R {};
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3460 oluşturur.

```
// C3460_b.cpp
// compile with: /clr /c
#using "C3460.dll"
[assembly:TypeForwardedTo(int::typeid)];   // C3460
[assembly:TypeForwardedTo(R::typeid)];
```