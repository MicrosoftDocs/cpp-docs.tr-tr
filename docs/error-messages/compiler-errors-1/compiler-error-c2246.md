---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2246'
title: Derleyici hatası C2246
ms.date: 11/04/2016
f1_keywords:
- C2246
helpviewer_keywords:
- C2246
ms.assetid: 4f3e4f83-21f3-4256-af96-43e0bb060311
ms.openlocfilehash: 1868389c98dd864e7d92bf33d57dbe96b831f3e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302218"
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
