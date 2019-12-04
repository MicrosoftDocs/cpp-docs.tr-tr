---
title: Derleyici hatası C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: b51b556ea576e02b85a5c2ee5032909af39c7b2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758443"
---
# <a name="compiler-error-c2133"></a>Derleyici hatası C2133

' tanımlayıcı ': Bilinmeyen boyut

Boyutlandırılmış olmayan bir dizi, bir sınıf, yapı, birleşim veya numaralandırma üyesi olarak belirtilir. /Za (ANSI C) seçeneği, boyutlandırılabilen üye dizilerine izin vermez.

Aşağıdaki örnek C2133 oluşturur:

```cpp
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

Olası çözüm:

```cpp
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```
