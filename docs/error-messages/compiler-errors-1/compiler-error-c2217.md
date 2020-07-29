---
title: Derleyici hatası C2217
ms.date: 11/04/2016
f1_keywords:
- C2217
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
ms.openlocfilehash: b033d95b127a45451a776cdc336ea7d2649d3716
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209753"
---
# <a name="compiler-error-c2217"></a>Derleyici hatası C2217

' Attribute1 ', ' attribute2 ' gerektirir

İlk işlev özniteliği ikinci özniteliği gerektirir.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Interrupt ( `__interrupt` ) işlevi olarak bildirilmiştir `near` . Kesme işlevleri olmalıdır `far` .

1. Veya ile belirtilen kesme işlevi **`__stdcall`** **`__fastcall`** . Kesme işlevlerinin C çağrı kurallarını kullanması gerekir.

## <a name="example"></a>Örnek

C2217, bir temsilciyi değişken sayıda bağımsız değişken alan bir CLR işlevine bağlamayı denerseniz da oluşabilir. İşlevin aynı zamanda e param dizi aşırı yüklemesi de varsa bunu kullanın. Aşağıdaki örnek C2217 oluşturur.

```cpp
// C2217.cpp
// compile with: /clr
using namespace System;
delegate void MyDel(String^, Object^, Object^, ...);   // C2217
delegate void MyDel2(String ^, array<Object ^> ^);   // OK

int main() {
   MyDel2^ wl = gcnew MyDel2(Console::WriteLine);
   array<Object ^ > ^ x = gcnew array<Object ^>(2);
   x[0] = safe_cast<Object^>(0);
   x[1] = safe_cast<Object^>(1);

   // wl("{0}, {1}", 0, 1);
   wl("{0}, {1}", x);
}
```
