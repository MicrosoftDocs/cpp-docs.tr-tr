---
title: Derleyici Hatası C2228 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2228
dev_langs:
- C++
helpviewer_keywords:
- C2228
ms.assetid: 901cadb1-ce90-4ae0-a360-547a9ba2ca18
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 70ea4fcdf2647264550b32ce941a3551664a6b94
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082889"
---
# <a name="compiler-error-c2228"></a>Derleyici Hatası C2228

sol tarafında '.identifier' sınıf/yapı/birleşim olmalıdır

Nokta (.) sol işlenen bir sınıf, yapı veya birleşim değil.

Aşağıdaki örnek, C2228 oluşturur:

```
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

Yönetilen Uzantılar kullanırken sözdizimi yanlış kullanırsanız, bu hatayı görürsünüz. Diğer Visual Studio dillerinde nokta işleci yönetilen sınıfının bir üyesine erişmek için kullanabilirsiniz, ancak sahip kullanmak c++ nesne işaretçisi anlamına gelir -> işleci bir üyesine erişmek için:

Sorun: `String * myString = checkedListBox1->CheckedItems->Item[0].ToString();`

Sağ: `String * myString = checkedListBox1->CheckedItems->Item[0]->ToString();`