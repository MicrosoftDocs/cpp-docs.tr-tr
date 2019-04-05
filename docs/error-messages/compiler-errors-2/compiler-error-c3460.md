---
title: Derleyici Hatası C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: 9ffbc5102855574aba668a2c501cd08dbaebe5b8
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58775185"
---
# <a name="compiler-error-c3460"></a>Derleyici Hatası C3460

'type': yalnızca bir kullanıcı tanımlı bir tür iletilebilir

Daha fazla bilgi için [tür iletme (C + +/ CLI)](../../extensions/type-forwarding-cpp-cli.md).

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