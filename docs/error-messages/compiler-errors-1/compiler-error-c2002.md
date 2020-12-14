---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2002'
title: Derleyici hatası C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: acf6e0679f2579d25d37ccf0c11965bc1d8b436a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298623"
---
# <a name="compiler-error-c2002"></a>Derleyici hatası C2002

geçersiz geniş karakter sabiti

Çok baytlı karakter sabiti geçerli değil.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. Geniş karakter sabiti beklenenden daha fazla bayt içeriyor.

1. Standart üstbilgi STDDEF. h dahil değildir.

1. Geniş karakterler normal dize sabit değerleri ile birleştirilemez.

1. Geniş karakterli bir sabit öncesinde ' L ' karakteri gelmelidir:

    ```
    L'mbconst'
    ```

1. Microsoft C++ için, bir Önişlemci yönergesinin metin bağımsız değişkenleri ASCII olmalıdır. Örneğin, yönergesi `#pragma message(L"string")` geçerli değildir.
