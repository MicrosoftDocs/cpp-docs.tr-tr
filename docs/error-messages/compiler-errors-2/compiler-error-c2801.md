---
title: Derleyici hatası C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: cfb89c79534318ab1fbcaa06667d594bfe2f1157
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214600"
---
# <a name="compiler-error-c2801"></a>Derleyici hatası C2801

' işleç işleci ' statik olmayan bir üye olmalıdır

Aşağıdaki işleçler yalnızca statik olmayan üyeler olarak aşırı yüklenebilir:

- Atanmış`=`

- Sınıf üyesi erişimi`->`

- Alt simge oluşturma`[]`

- İşlev çağrısı`()`

Olası C2801 nedenler:

- Aşırı yüklenmiş işleç bir sınıf, yapı veya birleşim üyesi değil.

- Aşırı yüklenmiş işleç bildirilmiştir **`static`** .

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
