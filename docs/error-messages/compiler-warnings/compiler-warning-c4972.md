---
title: Derleyici Uyarısı C4972
ms.date: 11/04/2016
f1_keywords:
- C4972
helpviewer_keywords:
- C4972
ms.assetid: d18e8e65-b2ef-4d75-a207-fbd0c17c9060
ms.openlocfilehash: 7c58258298fb91d04014e719732135a1f33f13b6
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777906"
---
# <a name="compiler-warning-c4972"></a>Derleyici Uyarısı C4972

Doğrudan değiştirme ya da açma işleminin sonucu lvalue olarak değerlendirmek doğrulanamaz

Bir değer türü için bir tanıtıcı başvurusunun kaldırılması, olarak da bilinen kutudan çıkarma ve kendisine atama doğrulanabilir değil.

Daha fazla bilgi için [kutulama](../../extensions/boxing-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4972 oluşturur.

```
// C4972.cpp
// compile with: /clr:safe
using namespace System;
ref struct R {
   int ^ p;   // a value type
};

int main() {
   R ^ r = gcnew R;
   *(r->p) = 10;   // C4972

   // OK
   r->p = 10;
   Console::WriteLine( r->p );
   Console::WriteLine( *(r->p) );
}
```