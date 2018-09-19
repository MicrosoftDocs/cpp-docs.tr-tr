---
title: Derleyici Hatası C2002 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b87a7fe1513c695344676624ae1968060097c885
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116925"
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