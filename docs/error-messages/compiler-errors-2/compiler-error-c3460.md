---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3460'
title: Derleyici hatası C3460
ms.date: 11/04/2016
f1_keywords:
- C3460
helpviewer_keywords:
- C3460
ms.assetid: adbf8775-10ca-4654-acdf-58dd765351cd
ms.openlocfilehash: ee5bcb2396586d965f16d80ef006301c7bcd784f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315887"
---
# <a name="compiler-error-c3460"></a>Derleyici hatası C3460

' Type ': yalnızca Kullanıcı tanımlı bir tür iletilebilir

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3460.cpp
// compile with: /LD /clr
public ref class R {};
```

Aşağıdaki örnek C3460 oluşturur.

```cpp
// C3460_b.cpp
// compile with: /clr /c
#using "C3460.dll"
[assembly:TypeForwardedTo(int::typeid)];   // C3460
[assembly:TypeForwardedTo(R::typeid)];
```
