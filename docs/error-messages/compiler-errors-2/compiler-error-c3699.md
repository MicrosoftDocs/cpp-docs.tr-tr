---
title: Derleyici Hatası C3699
ms.date: 11/04/2016
f1_keywords:
- C3699
helpviewer_keywords:
- C3699
ms.assetid: 47c29afc-ab8b-4238-adfe-788dd6e00b3b
ms.openlocfilehash: 93058d34ca9a17ab175a55a7bc7b953d369e65c5
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "58776745"
---
# <a name="compiler-error-c3699"></a>Derleyici Hatası C3699

'operator': Bu yöneltme 'type' türü üzerinde kullanılamaz

İzin verilmez yöneltme kullanmak için bir girişimde bulunuldu `type`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3699 oluşturur.

```
// C3699.cpp
// compile with: /clr /c
using namespace System;
int main() {
   String * s;   // C3699
   // try the following line instead
   // String ^ s2;
}
```

## <a name="example"></a>Örnek

Önemsiz özellik başvuru türüne sahip olamaz. Bkz: [özelliği](../../extensions/property-cpp-component-extensions.md) daha fazla bilgi için. Aşağıdaki örnek, C3699 oluşturur.

```
// C3699_b.cpp
// compile with: /clr /c
ref struct C {
   property System::String % x;   // C3699
   property System::String ^ y;   // OK
};
```

## <a name="example"></a>Örnek

Bir tanıtıcı izleme başvurusu için bir "bir işaretçi işaretçisi" söz dizimi eşdeğerdir. Aşağıdaki örnek, C3699 oluşturur.

```
// C3699_c.cpp
// compile with: /clr /c
using namespace System;
void Test(String ^^ i);   // C3699
void Test2(String ^% i);
```