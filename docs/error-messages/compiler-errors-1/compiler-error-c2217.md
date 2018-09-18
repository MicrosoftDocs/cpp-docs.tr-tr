---
title: Derleyici Hatası C2217 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2217
dev_langs:
- C++
helpviewer_keywords:
- C2217
ms.assetid: 1ce1e3f5-4171-4376-804d-967f7e612935
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a4eb8b9fcaffa30f3a5ced5362a0f9d54a45f07e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050625"
---
# <a name="compiler-error-c2217"></a>Derleyici Hatası C2217

'öznitelik1' 'öznitelik2' gerektirir

İkinci öznitelik ilk işlevi özniteliği gerektirir.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Kesme (`__interrupt`) olarak bildirilen işlev `near`. Kesme işlevleri olmalıdır `far`.

1. İle bildirilen işlevde kesme `__stdcall`, veya `__fastcall`. İşlev kesme kullanmak C çağrı kuralları gerekir.

## <a name="example"></a>Örnek

Değişken sayıda bağımsız değişken alan bir CLR işlevi için temsilci bağlamak çalışırsanız C2217 da meydana gelebilir. İşlevi ayrıca e param dizisi aşırı yükleme varsa, bunun yerine kullanın. Aşağıdaki örnek, C2217 oluşturur.

```
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