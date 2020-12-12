---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3461'
title: Derleyici hatası C3461
ms.date: 11/04/2016
f1_keywords:
- C3461
helpviewer_keywords:
- C3461
ms.assetid: bd66833a-545d-445a-bdfe-dee771a450a4
ms.openlocfilehash: 6158e0d6d38290a1925beba89fe77cba8f01c87b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113500"
---
# <a name="compiler-error-c3461"></a>Derleyici hatası C3461

' Type ': yalnızca bir yönetilen tür iletilebilir

Tür iletme yalnızca CLR türlerinde olabilir.  Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md) .

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3461.cpp
// compile with: /clr /LD
public ref class R {};
```

Aşağıdaki örnek C3461 oluşturur.

```cpp
// C3461b.cpp
// compile with: /clr /c
#using "C3461.dll"
class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3461
[assembly:TypeForwardedTo(R::typeid)];   // OK
```
