---
description: 'Daha fazla bilgi edinin: önemli hata C1070'
title: Önemli hata C1070
ms.date: 11/04/2016
f1_keywords:
- C1070
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
ms.openlocfilehash: 2668bfa6c24c602606cbd9ee41b5322272eec093
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344399"
---
# <a name="fatal-error-c1070"></a>Önemli hata C1070

' filename ' dosyasında eşleşmeyen #if/#endif çifti

`#if`, `#ifdef` Veya `#ifndef` yönergesinin karşılık gelen bir `#endif` .

Aşağıdaki örnek C1070 oluşturur:

```cpp
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

Olası çözüm:

```cpp
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```
