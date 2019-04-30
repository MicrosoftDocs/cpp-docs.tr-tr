---
title: Derleyici Hatası C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: a65e3c0ea622950b99b9ba83fc168b4718d13e46
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345716"
---
# <a name="compiler-error-c2085"></a>Derleyici Hatası C2085

'identifier': biçimsel parametre listesinde değil

Tanımlayıcı, bir işlev tanımında ancak biçimsel parametre listesinde bildirildi. (Yalnızca ANSI C)

Aşağıdaki örnek, C2085 oluşturur:

```
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Olası çözüm:

```
// C2085b.c
void func1( void );
int main( void ) {}
```

Noktalı virgül eksik olan `func1()` bu nedenle bir prototipi bir işlev tanımı gibi görünüyor `main` içinde tanımlanan `func1()`, hatası C2085 tanımlayıcısı oluşturma `main`.