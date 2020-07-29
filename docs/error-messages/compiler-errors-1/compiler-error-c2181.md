---
title: Derleyici hatası C2181
ms.date: 11/04/2016
f1_keywords:
- C2181
helpviewer_keywords:
- C2181
ms.assetid: d52b2fe4-566a-40a9-b8e2-8dce1f287668
ms.openlocfilehash: e1ad2451d1530707920e2d80ab68eece516f2562
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87209967"
---
# <a name="compiler-error-c2181"></a>Derleyici hatası C2181

eşleşmeyen if olmayan geçersiz Else

Her birinin **`else`** bir eşleşen olması gerekir **`if`** .

Aşağıdaki örnek C2181 oluşturur:

```cpp
// C2181.cpp
int main() {
   int i = 0;
   else   // C2181
      i = 1;
}
```

Olası çözüm:

```cpp
// C2181b.cpp
int main() {
   int i = 0;
   if(i)
      i = 0;
   else
      i = 1;
}
```
