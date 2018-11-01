---
title: Önemli hata C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: f3c9f9bde5da7fb120accbb9a8d72e5715ab9d2b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569703"
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081

'symbol': dosya adı çok uzun

Bir dosya yol uzunluğunu aşıyor `_MAX_PATH` (260 karakter olarak Stdlıb.h tarafından tanımlanır). Dosya adını kısaltın.

Kısa bir adla CL.exe çağırırsanız, derleyici bir tam yol üretmek gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin neden olabilir:

```
D:\<very-long-directory-path>\myfile.cpp
```