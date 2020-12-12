---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3699'
title: Derleyici hatası C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: 670b5c41aad9afcece8d8cd292727ad64925a4ab
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228722"
---
# <a name="compiler-error-c3699"></a>Derleyici hatası C3699

' operator ': Bu yöneltme ' Type ' türü üzerinde kullanılamaz

Üzerinde izin verilmeyen bir yöneltme kullanma girişiminde bulunuldu `type` .

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3699 oluşturur.

```cpp
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

Önemsiz bir özellik başvuru türüne sahip olamaz. Daha fazla bilgi için bkz. [özelliği](../../extensions/property-cpp-component-extensions.md) . Aşağıdaki örnek C3699 oluşturur.

```cpp
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

Bir "işaretçi işaretçisinin" söz dizimi, izleme başvurusunun bir tanıtıcıdır. Aşağıdaki örnek C3699 oluşturur.

```cpp
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```
