---
title: Derleyici hatası C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: c7dac0abb7d65d3f26522ea1a04577643b7b9eca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212832"
---
# <a name="compiler-error-c2246"></a>Derleyici hatası C2246

' tanımlayıcı ': yerel olarak tanımlanan sınıfta geçersiz statik veri üyesi

Yerel kapsama sahip bir sınıf, yapı veya birleşim üyesi bildirilmiştir **`static`** .

Aşağıdaki örnek C2246 oluşturur:

```cpp
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```
