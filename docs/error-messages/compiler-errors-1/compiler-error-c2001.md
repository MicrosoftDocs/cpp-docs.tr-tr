---
title: Derleyici Hatası C2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2001
dev_langs:
- C++
helpviewer_keywords:
- C2001
ms.assetid: 0c3a7821-d8e5-4398-ab5a-4116d46e8dda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 71048a706678e4d9e6906972ebf148748927e829
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088248"
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