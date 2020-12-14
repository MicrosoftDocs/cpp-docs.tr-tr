---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2581'
title: Derleyici hatası C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: 9de6c48c2ade71af238cc62a0f92e642e1262d3b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282126"
---
# <a name="compiler-error-c2581"></a>Derleyici hatası C2581

' Type ': statik ' operator = ' işlevi geçersizdir

Atama ( `=` ) işleci yanlış olarak bildirilmiştir **`static`** . Atama işleçleri olamaz **`static`** . Daha fazla bilgi için bkz. [Kullanıcı tanımlı işleçler (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C2581 oluşturur.

```cpp
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```
