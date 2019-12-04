---
title: Derleyici hatası C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 0d2ea3677d883fa4843c37a41d733872b23cbba0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760679"
---
# <a name="compiler-error-c2801"></a>Derleyici hatası C2801

' işleç işleci ' statik olmayan bir üye olmalıdır

Aşağıdaki işleçler yalnızca statik olmayan üyeler olarak aşırı yüklenebilir:

- Atama `=`

- Sınıf üyesi erişimi `->`

- `[]` alt simge oluşturma

- İşlev çağrısı `()`

Olası C2801 nedenler:

- Aşırı yüklenmiş işleç bir sınıf, yapı veya birleşim üyesi değil.

- Aşırı yüklenmiş operatör `static`olarak bildirilmiştir.

- Aşağıdaki örnek C2801 oluşturur:

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
