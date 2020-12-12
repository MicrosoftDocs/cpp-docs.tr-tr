---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3181'
title: Derleyici hatası C3181
ms.date: 11/04/2016
f1_keywords:
- C3181
helpviewer_keywords:
- C3181
ms.assetid: 5d450f8b-6cef-4452-a0c4-2076e967451d
ms.openlocfilehash: b9b9c6e8c6271abbea2d97adf92f33c35eb2028b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174136"
---
# <a name="compiler-error-c3181"></a>Derleyici hatası C3181

' Type ': işleç için geçersiz işlenen

[TypeId](../../extensions/typeid-cpp-component-extensions.md) işlecine geçersiz bir parametre geçirildi. Parametrenin yönetilen bir tür olması gerekir.

Derleyicinin ortak dil çalışma zamanındaki türlerle eşlenen yerel türler için takma adlar kullandığını unutmayın.

Aşağıdaki örnek C3181 oluşturur:

```cpp
// C3181a.cpp
// compile with: /clr
using namespace System;

int main() {
   Type ^pType1 = interior_ptr<int>::typeid;   // C3181
   Type ^pType2 = int::typeid;   // OK
}
```
