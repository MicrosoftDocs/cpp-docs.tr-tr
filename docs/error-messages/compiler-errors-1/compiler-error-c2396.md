---
title: Derleyici hatası C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 5020732ce5186ee1c6e9d2ea13f452fe9988bdfa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74744842"
---
# <a name="compiler-error-c2396"></a>Derleyici hatası C2396

' your_type:: operator'type ' ': CLR veya WinRT Kullanıcı tanımlı dönüştürme functionvalid geçerli değil. Ya dönüştürmeniz gerekir: 'T ^ ', 't ^% ', 'T ^ & ', burada T = ' your_type '

Windows Çalışma Zamanı veya yönetilen türdeki bir dönüştürme işlevinde, türü dönüştürme işlevini içeren türle aynı olan en az bir parametre yoktu.

Aşağıdaki örnek C2396 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2396.cpp
// compile with: /clr /c

ref struct Y {
   static operator int(char c);   // C2396

   // OK
   static operator int(Y^ hY);
   // or
   static operator Y^(char c);
};
```
