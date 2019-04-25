---
title: Derleyici Hatası C2005
ms.date: 11/04/2016
f1_keywords:
- C2005
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
ms.openlocfilehash: 49d0375d5733410d728797d2a881075377b33ba6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209009"
---
# <a name="compiler-error-c2005"></a>Derleyici Hatası C2005

\#Satır 'belirteci' bulunan bir satır numarası bekliyordu

`#line` Yönergesi tarafından bir satır numarası gelmelidir.

Aşağıdaki örnek, C2005 oluşturur:

```
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

Olası çözüm:

```
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```