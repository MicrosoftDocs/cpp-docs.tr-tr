---
title: Derleyici Hatası C2659
ms.date: 11/04/2016
f1_keywords:
- C2659
helpviewer_keywords:
- C2659
ms.assetid: b0883600-4d27-4ca7-a931-8ca6bd48654d
ms.openlocfilehash: b8b6493b01ac2b88ea50ba50157328f59fdbedf9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360391"
---
# <a name="compiler-error-c2659"></a>Derleyici Hatası C2659

'işleç': sol işlenen olarak işlev

Bir işlev, belirtilen işlecin sol tarafındaydı. Bu hatanın en yaygın nedeni, derleyicinin tanımlayıcıyı işlecin son tarafında işlev olarak ayrıştırmasıdır, fakat geliştiricinin aslında onu bir değişken yapmayı hedeflemesidir. Daha fazla bilgi için bkz. Wikipedia makalesi [En zorlu ayrıştırma](http://en.wikipedia.org/wiki/Most_vexing_parse). Bu örnekte, kolaylıkla birbiriyle karıştırılabilecek bir işlev bildirimi ve değişken tanımı gösterilmiştir:

```
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

```
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