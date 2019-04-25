---
title: Derleyici Hatası C2396
ms.date: 11/04/2016
f1_keywords:
- C2396
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
ms.openlocfilehash: d320f78937fc60910bbed4a5b1b89841ea674fb7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62303521"
---
# <a name="compiler-error-c2396"></a>Derleyici Hatası C2396

' your_type::operator'type'': CLR veya WinRT kullanıcı tanımlı dönüştürme functionnot geçerli. Dönüştürmek veya Dönüştür: 'T ^', 'T ^ %', 'T ^ &', burada T = 'your_type'

Bir Windows çalışma zamanı veya yönetilen türü bir dönüştürme işlevi türü dönüştürme işlevi içeren türle aynı olan en az bir parametre yok.

Aşağıdaki örnek, C2396 oluşturur ve bu sorunun nasıl gösterir:

```
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