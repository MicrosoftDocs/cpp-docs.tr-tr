---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3464'
title: Derleyici hatası C3464
ms.date: 11/04/2016
f1_keywords:
- C3464
helpviewer_keywords:
- C3464
ms.assetid: 0ede05dc-4486-4921-8e8c-78ab5a2e09c5
ms.openlocfilehash: 893fc5b0afa3f389d5b85757abb903323cd0d780
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97315770"
---
# <a name="compiler-error-c3464"></a>Derleyici hatası C3464

' Type ' iç içe geçmiş bir tür iletilemez

Tür iletme iç içe türler üzerinde çalışmıyor.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3464.cpp
// compile with: /LD /clr
public ref class R {
public:
   ref class N {};
};
```

Aşağıdaki örnek C3464 oluşturur.

```cpp
// C3464_b.cpp
// compile with: /clr /c
#using "C3464.dll"
[assembly:TypeForwardedTo(R::N::typeid)];   // C3464
[assembly:TypeForwardedTo(R::typeid)];   // OK
```
