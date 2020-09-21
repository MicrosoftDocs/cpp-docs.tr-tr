---
title: Derleyici hatası C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 7493934879068109c582a85592f485c1d391e2de
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743392"
---
# <a name="compiler-error-c2761"></a>Derleyici hatası C2761

' function ': üye işlev yeniden bildirimine izin verilmiyor

Bir üye işlevini yeniden bildiremezsiniz. Bunu tanımlayabilir ancak yeniden bildiremezsiniz.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2761 oluşturur.

```cpp
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761
```

Bir sınıfın veya yapının statik olmayan üyeleri tanımlanamıyor.  Aşağıdaki örnek C2761 oluşturur.

```cpp
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```
