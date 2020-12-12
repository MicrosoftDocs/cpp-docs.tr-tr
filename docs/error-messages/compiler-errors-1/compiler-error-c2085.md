---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2085'
title: Derleyici hatası C2085
ms.date: 11/04/2016
f1_keywords:
- C2085
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
ms.openlocfilehash: 2cd828c9a18c06c5794bef01ba861f702af2e096
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252122"
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

Noktalı virgül eksik olan, `func1()` prototip değil işlev tanımı gibi görünüyor, bu nedenle `main` içinde tanımlanmıştır, `func1()` tanımlayıcı için hata C2085 oluşturuluyor `main` .
