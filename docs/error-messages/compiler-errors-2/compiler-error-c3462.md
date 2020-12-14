---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3462'
title: Derleyici hatası C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: e201dc9d999438053d5fd8d70813360c28a534df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315796"
---
# <a name="compiler-error-c3462"></a>Derleyici hatası C3462

' Type ': yalnızca içeri aktarılan bir tür iletilebilir

TypeForwardedTo özniteliği başvurulan meta verilerde bir türe uygulanmalıdır.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

Aşağıdaki örnek C3462 oluşturur.

```cpp
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```
