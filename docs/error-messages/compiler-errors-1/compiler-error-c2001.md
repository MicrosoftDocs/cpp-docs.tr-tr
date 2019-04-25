---
title: Derleyici Hatası C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 03b54fe2373063c8c0f9905da93822928392998d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209029"
---
# <a name="compiler-error-c2001"></a>Derleyici Hatası C2001

Sabitte

Aşağıdakileri sürece bir dize sabitine ikinci satırında devam ettirilemez:

- İlk satır bir ters eğik çizgi ile bitmelidir.

- Çift tırnak işareti ile ilk satırdaki dize kapatın ve çift tırnak işareti ile başka bir sonraki satıra dize açın.

İlk satırı \n ile biten yeterli değildir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2001 oluşturur:

```
// C2001.cpp
// C2001 expected
#include <stdio.h>

int main()
{
    printf_s("Hello,
             world");
    printf_s("Hello,\n
             world");
}
```

## <a name="example"></a>Örnek

Satır devamlılığı karakteri sonra sonraki satırın başında boşluk dize sabiti dahil edilir. Yukarıda gösterilen örneklerden hiçbiri bir yeni satır karakteri dize sabitine ekleyin. Burada gösterildiği gibi bir yeni satır karakteri ekleyebilirsiniz:

```
// C2001b.cpp
#include <stdio.h>

int main()
{
    printf_s("Hello,\n\
             world");

    printf_s("Hello,\
             \nworld");

    printf_s("Hello,\n"
             "world");

    printf_s("Hello,"
             "\nworld");

    printf_s("Hello,"
             " world");

    printf_s("Hello,\
             world");
}
```