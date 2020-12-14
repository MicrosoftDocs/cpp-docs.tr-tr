---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2659'
title: Derleyici hatası C2659
ms.date: 11/04/2016
f1_keywords:
- C2659
helpviewer_keywords:
- C2659
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
ms.openlocfilehash: 6a0f6c84e6bc279d9db75c423fdfc0d99b5ea769
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249678"
---
# <a name="compiler-error-c2659"></a>Derleyici hatası C2659

'işleç': sol işlenen olarak işlev

Bir işlev, belirtilen işlecin sol tarafındaydı. Bu hatanın en yaygın nedeni, derleyicinin tanımlayıcıyı işlecin son tarafında işlev olarak ayrıştırmasıdır, fakat geliştiricinin aslında onu bir değişken yapmayı hedeflemesidir. Daha fazla bilgi için bkz. [en çok vexlama ayrıştırma](https://en.wikipedia.org/wiki/Most_vexing_parse)makalesi. Bu örnekte, kolaylıkla birbiriyle karıştırılabilecek bir işlev bildirimi ve değişken tanımı gösterilmiştir:

```cpp
// C2659a.cpp
// Compile using: cl /W4 /EHsc C2659a.cpp
#include <string>
using namespace std;

int main()
{
   string string1(); // string1 is a function returning string
   string string2{}; // string2 is a string initialized to empty

   string1 = "String 1"; // C2659
   string2 = "String 2";
}
```

Bu sorunu gidermek için, tanımlayıcının bildirimini işlev bildirimi olarak ayrıştırılmayacak şekilde değiştirin.

Hata C2659, işlev, belirtilen işlecin sol tarafındaki ifadede kullanılamayan bir türe sahip olduğunda da meydana gelebilir. Bu örnek, kod bir işleve işlev işaretçisi atarken C2659 oluşturur:

```cpp
// C2659b.cpp
// Compile using: cl /W4 /EHsc C2659b.cpp
int func0(void) { return 42; }
int (*func1)(void);

int main()
{
   func1 = func0;
   func0 = func1; // C2659
}
```
