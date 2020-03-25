---
title: Önemli hata C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: b8630a26d14c68a5f1abe45bb0b8d0141d0dedbb
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80204197"
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081

' symbol ': dosya adı çok uzun

Bir dosya yol adının uzunluğu `_MAX_PATH` (STDLIB. h tarafından 260 karakter olarak tanımlanır) aşıyor. Dosyanın adını kısaltın.

CL. exe ' yi kısa bir dosya adıyla çağırırsanız, derleyicinin tam bir yol adı oluşturması gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin oluşturmasına neden olabilir:

```
D:\<very-long-directory-path>\myfile.cpp
```
