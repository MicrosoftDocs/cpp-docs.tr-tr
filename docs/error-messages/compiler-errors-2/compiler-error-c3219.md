---
title: Derleyici Hatası C3219
ms.date: 11/04/2016
f1_keywords:
- C3219
helpviewer_keywords:
- C3219
ms.assetid: 9c9757b0-1256-4cdf-9d8c-a3a72f300ce5
ms.openlocfilehash: a93e9ed1a8e00eaecc664bda02a70c81b6c81ded
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621695"
---
# <a name="compiler-error-c3219"></a>Derleyici Hatası C3219

'param': genel parametre birden fazla arabirim olmayan öğe tarafından kısıtlanamaz: 'class'

Genel parametre tarafından yönetilen iki veya daha fazla sınıflar sınırlamak için geçerli değil.

Aşağıdaki örnek, C3219 oluşturur:

```
// C3219.cpp
// compile with: /clr
ref class A {};
ref class B {};

generic <class T>
where T : A, B
ref class E {};   // C3219
```

Aşağıdaki örnek, olası çözümü göstermektedir:

```
// C3219b.cpp
// compile with: /clr /c
ref class A {};

interface struct C {};

generic <class T>
where T : A
ref class E {};
```