---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2228'
title: Derleyici hatası C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 8bf5c4af88f77237699baae5e7a458fca971f126
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195066"
---
# <a name="compiler-error-c2228"></a>Derleyici hatası C2228

'. Identifier ' sol tarafında Class/struct/Union olmalıdır

Dönemin solundaki işlenen (.) bir sınıf, yapı veya birleşim değil.

Aşağıdaki örnek C2228 oluşturur:

```cpp
// C2228.cpp
int i;
struct S {
public:
    int member;
} s, *ps = &s;

int main() {
   i.member = 0;   // C2228 i is not a class type
   ps.member = 0;  // C2228 ps is a pointer to a structure

   s.member = 0;   // s is a structure type
   ps->member = 0; // ps points to a structure S
}
```

Ayrıca, yönetilen uzantıları kullanırken yanlış söz dizimi kullanırsanız bu hatayı görürsünüz. Diğer Visual Studio dillerinde, yönetilen bir sınıfın üyesine erişmek için nokta işlecini kullanabilirsiniz, C++ ' ta nesnenin bir işaretçisi, üyeye erişmek için-> işlecini kullanmanız gerektiği anlamına gelir:

Yanlış `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

Right `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
