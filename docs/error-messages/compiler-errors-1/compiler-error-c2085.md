---
title: Derleyici hatası C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 7dbf7266a6330a1fdb46d7f2df90e7684f026d9a
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301970"
---
# <a name="compiler-error-c2085"></a>Derleyici hatası C2085

' tanımlayıcı ': biçimsel parametre listesinde değil

Tanımlayıcı, biçimsel parametre listesinde değil, bir işlev tanımında bildirildi. (Yalnızca ANSI C)

Aşağıdaki örnek C2085 oluşturur:

```c
// C2085.c
void func1( void )
int main( void ) {}   // C2085
```

Olası çözüm:

```c
// C2085b.c
void func1( void );
int main( void ) {}
```

Noktalı virgül eksik olan `func1()`, prototip değil bir işlev tanımı gibi görünür, bu nedenle `main` `func1()`içinde tanımlanır ve tanımlayıcı `main`için hata C2085 oluşturuluyor.
