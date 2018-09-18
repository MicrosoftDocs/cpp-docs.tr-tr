---
title: Derleyici Uyarısı (düzey 4) C4706 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4706
dev_langs:
- C++
helpviewer_keywords:
- C4706
ms.assetid: 89cd3f4f-812c-4a4b-9426-65a5a6d1b99c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 843edeaf490f27475003e9303f7929b818e2b104
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036962"
---
# <a name="compiler-warning-level-4-c4706"></a>Derleyici Uyarısı (düzey 4) C4706

Koşullu ifadeyle atama

Koşullu ifadede test sonucu atama değerindeydi.

Atama test ifade dahil olmak üzere başka bir ifadede, yasal olarak kullanılabilecek bir değeri (atamasının sol tarafta) sahiptir.

Aşağıdaki örnek, C4706 oluşturur:

```
// C4706a.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a  = b ) // C4706
   {
   }
}
```

Test koşulunu parantezler çift bile uyarısı meydana gelir:

```
// C4706b.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a  =  b ) ) // C4706
   {
   }
}
```

Bir ilişki test ve bir atama olmamasını istiyorsanız `==` işleci. Örneğin, aşağıdaki testleri olup satır bir ve b eşit:

```
// C4706c.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( a == b )
   {
   }
}
```

Atama sonucu değeri test yapmak istiyorsanız, atama sıfır olmayan veya null olduğundan emin olmak için test edin. Örneğin, aşağıdaki kod bu uyarıyı oluşturmaz:

```
// C4706d.cpp
// compile with: /W4
int main()
{
   int a = 0, b = 0;
   if ( ( a = b ) != 0 )
   {
   }
}
```