---
title: Derleyici Hatası C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 44f7988f9fedb882972b2823f2fe70d9512d4e87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484792"
---
# <a name="compiler-error-c2801"></a>Derleyici Hatası C2801

'operator işleci' statik olmayan üye olmanız gerekir

Aşağıdaki işleçleri yalnızca statik olmayan üye olarak aşırı yüklenebilir:

- Atama `=`

- Sınıf üyesi erişimi `->`

- Subscripting `[]`

- İşlev çağrısı `()`

Olası C2801 neden olur:

- Aşırı yüklenmiş işleç, bir sınıf, yapı veya birleşim üyesi değil.

- Aşırı yüklenmiş işleç bildirilmiş `static`.

- Aşağıdaki örnek, C2801 oluşturur:

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```