---
title: Derleyici hatası C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: 89352029afbae4d977a4109f76c0e18bb761b4d4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758924"
---
# <a name="compiler-error-c2246"></a>Derleyici hatası C2246

' tanımlayıcı ': yerel olarak tanımlanan sınıfta geçersiz statik veri üyesi

Yerel kapsamlı bir sınıf, yapı veya birleşim üyesi `static`olarak bildirilmiştir.

Aşağıdaki örnek C2246 oluşturur:

```cpp
// C2246.cpp
// compile with: /c
void func( void ) {
   class A { static int i; };   // C2246  i is local to func
   static int j;   // OK
};
```
