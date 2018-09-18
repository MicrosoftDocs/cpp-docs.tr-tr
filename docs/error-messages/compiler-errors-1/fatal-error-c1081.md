---
title: Önemli hata C1081 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1081
dev_langs:
- C++
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b34f2f19a0bb8770ea9292fef120c415c0fb255a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060541"
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081

'symbol': dosya adı çok uzun

Bir dosya yol uzunluğunu aşıyor `_MAX_PATH` (260 karakter olarak Stdlıb.h tarafından tanımlanır). Dosya adını kısaltın.

Kısa bir adla CL.exe çağırırsanız, derleyici bir tam yol üretmek gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin neden olabilir:

```
D:\<very-long-directory-path>\myfile.cpp
```