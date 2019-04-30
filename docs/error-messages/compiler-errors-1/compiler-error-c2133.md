---
title: Derleyici Hatası C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: 68672ae76024d3d09d738d997c485a3205c7dd2a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62397581"
---
# <a name="compiler-error-c2133"></a>Derleyici Hatası C2133

'identifier': Bilinmeyen boyut

Boyutsuz bir diziyi sınıfı, yapı, birleşim veya numaralandırma üyesi olarak bildirilir. /Za (ANSI C) seçeneğini boyutsuz üye dizileri izin vermez.

Aşağıdaki örnek, C2133 oluşturur:

```
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

Olası çözüm:

```
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```