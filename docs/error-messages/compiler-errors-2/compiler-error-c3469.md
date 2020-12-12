---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3469'
title: Derleyici hatası C3469
ms.date: 11/04/2016
f1_keywords:
- C3469
helpviewer_keywords:
- C3469
ms.assetid: e23b0e5c-c704-4e67-a868-bf02c2055d85
ms.openlocfilehash: 3a08cbc21405a78b6f624463c379d07860210b72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97113434"
---
# <a name="compiler-error-c3469"></a>Derleyici hatası C3469

' Type ': genel bir sınıf iletilemez

Genel bir sınıfta tür iletme kullanamazsınız.

Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek bir bileşen oluşturur.

```cpp
// C3469.cpp
// compile with: /clr /LD
generic<typename T>
public ref class GR {};

public ref class GR2 {};
```

Aşağıdaki örnek C3466 oluşturur.

```cpp
// C3469_b.cpp
// compile with: /clr /c
#using "C3469.dll"
[assembly:TypeForwardedTo(GR::typeid)];   // C3469
[assembly:TypeForwardedTo(GR2::typeid)];   // OK
```
