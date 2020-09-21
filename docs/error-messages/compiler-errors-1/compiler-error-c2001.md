---
title: Derleyici hatası C2001
ms.date: 11/04/2016
f1_keywords:
- C2001
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
ms.openlocfilehash: 6b40a3bd186b5c45a0ea5163f433635ab1e7b07f
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743496"
---
# <a name="compiler-error-c2001"></a>Derleyici hatası C2001

Sabitte yeni satır

Bir dize sabiti, aşağıdakilerden birini yapmadığınız müddetçe ikinci satırda devam ettirilemez:

- İlk satırı ters eğik çizgiyle sonlandırın.

- İlk satırdaki dizeyi çift tırnak işaretiyle kapatın ve sonraki satırdaki dizeyi başka bir çift tırnak işaretiyle açın.

\N ile ilk satırın sona ermek yeterli değildir.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2001 oluşturur:

```cpp
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

Bir satır devamlılık karakteri sonrasında sonraki satırın başındaki boşluklar dize sabitine dahildir. Yukarıda gösterilen örneklerden hiçbiri dize sabitine bir yeni satır karakteri ekleyin. Buraya gösterildiği gibi bir yeni satır karakteri ekleyebilirsiniz:

```cpp
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
