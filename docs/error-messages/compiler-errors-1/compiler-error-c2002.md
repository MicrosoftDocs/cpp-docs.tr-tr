---
title: Derleyici Hatası C2002
ms.date: 11/04/2016
f1_keywords:
- C2002
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
ms.openlocfilehash: 30f472aa7a9475a19eea0e92fe5c2ea0d54e382b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442854"
---
# <a name="compiler-error-c2002"></a>Derleyici Hatası C2002

Geçersiz geniş karakter sabiti

Çok baytlı karakter sabiti, geçerli değil.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için

1. Geniş karakter sabiti, beklenenden daha fazla bayt içerir.

1. Standart üstbilgi STDDEF.h dahil değildir.

1. Geniş karakterler, sıradan bir dize değişmez değerleri ile birleştirilmiş olamaz.

1. Bir geniş karakter sabiti 'L' karakteriyle gelmelidir:

    ```
    L'mbconst'
    ```

1. Microsoft C++ için ASCII önişlemci yönergesi metin bağımsız olmalıdır. Örneğin, yönergesi `#pragma message(L"string")`, geçerli değil.