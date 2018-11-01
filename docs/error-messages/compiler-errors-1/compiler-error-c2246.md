---
title: Derleyici Hatası C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c8efb71e0a39c56628fc582421e0f24ceb9b290c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464980"
---
# <a name="compiler-error-c2246"></a>Derleyici Hatası C2246

'identifier': yerel olarak tanımlanan sınıfta geçersiz statik veri üyesi

Bir sınıf, yapı veya birleşim yerel kapsama sahip bir üyesi bildirildiği `static`.

Aşağıdaki örnek, C2246 oluşturur:

```
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```