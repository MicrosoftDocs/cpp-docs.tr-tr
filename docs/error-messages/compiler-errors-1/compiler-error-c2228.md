---
title: Derleyici hatası C2228
ms.date: 11/04/2016
f1_keywords:
- C2228
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
ms.openlocfilehash: 56eed6aeff5a955253a440d5931d66118f4604e0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759288"
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

Ayrıca, yönetilen uzantıları kullanırken yanlış söz dizimi kullanırsanız bu hatayı görürsünüz. Diğer Visual Studio dillerinde, bir yönetilen sınıfın üyesine erişmek için nokta işlecini kullanabilirsiniz, içinde C++ nesnesine bir işaretçi, üyeye erişmek için-> işlecini kullanmanız gerekir:

Yanlış: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

Sağ: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`
