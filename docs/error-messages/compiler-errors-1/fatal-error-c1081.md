---
description: 'Daha fazla bilgi edinin: önemli hata C1081'
title: Önemli hata C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: 97e1070cb24a70750e9c7d9f78a3860b26a7831a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330696"
---
# <a name="fatal-error-c1081"></a>Önemli hata C1081

' symbol ': dosya adı çok uzun

Bir dosya yol adının uzunluğu `_MAX_PATH` (STDLIB. h tarafından 260 karakter olarak tanımlanır) aşılıyor. Dosyanın adını kısaltın.

CL.exe kısa bir dosya adıyla çağırırsanız, derleyicinin tam bir yol adı oluşturması gerekebilir. Örneğin, `cl -c myfile.cpp` derleyicinin oluşturmasına neden olabilir:

```
D:\<very-long-directory-path>\myfile.cpp
```
