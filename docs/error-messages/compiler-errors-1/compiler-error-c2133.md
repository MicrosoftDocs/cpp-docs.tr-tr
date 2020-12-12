---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2133'
title: Derleyici hatası C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: d98cb3bd8df5543ecf0426a146157300f67dd91b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323135"
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
