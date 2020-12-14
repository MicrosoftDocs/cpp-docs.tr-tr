---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2801'
title: Derleyici hatası C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: ca7e74f99b91b5a6699cdf3361ab64a89b7a7392
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297479"
---
# <a name="compiler-error-c2801"></a>Derleyici hatası C2801

' işleç işleci ' statik olmayan bir üye olmalıdır

Aşağıdaki işleçler yalnızca statik olmayan üyeler olarak aşırı yüklenebilir:

- Atanmış `=`

- Sınıf üyesi erişimi `->`

- Alt simge oluşturma `[]`

- İşlev çağrısı `()`

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
