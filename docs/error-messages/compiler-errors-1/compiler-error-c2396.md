---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2396'
title: Derleyici hatası C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: 654b812fbd152a6effb60e6f0919f99bf5039a1b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145398"
---
# <a name="compiler-error-c2396"></a>Derleyici hatası C2396

' your_type:: operator'type ' ': CLR veya WinRT Kullanıcı tanımlı dönüştürme functionvalid geçerli değil. Ya dönüştürmeniz gerekir: 'T ^ ', 't ^% ', 'T ^& ', burada T = ' your_type '

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
