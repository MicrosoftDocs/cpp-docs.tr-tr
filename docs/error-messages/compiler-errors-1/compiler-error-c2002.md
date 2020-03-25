---
title: Derleyici hatası C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: c37a9b94be837248c8025a4fc069d8a242128542
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208253"
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

1. Microsoft C++için, bir Önişlemci yönergesinin metin BAĞıMSıZ değişkenleri ASCII olmalıdır. Örneğin, `#pragma message(L"string")`yönergesi geçerli değildir.
