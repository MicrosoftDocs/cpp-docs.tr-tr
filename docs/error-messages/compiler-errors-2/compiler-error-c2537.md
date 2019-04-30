---
title: Derleyici Hatası C2537
ms.date: 11/04/2016
f1_keywords:
- C2537
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
ms.openlocfilehash: 437727b334087aef496dbb0a1f3f1c8cf2b45458
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345592"
---
# <a name="compiler-error-c2537"></a>Derleyici Hatası C2537

'belirticisi': Geçersiz bağlama belirtimi

Olası nedenler:

1. Bağlantı belirticisi desteklenmiyor. Yalnızca "C" bağlantı belirleyici desteklenir.

1. "C" bağlaması birden fazla işlev, aşırı yüklenmiş işlevler kümesi için belirtilir. Buna izin verilmez.

Aşağıdaki örnek, C2537 oluşturur:

```
// C2537.cpp
// compile with: /c
extern "c" void func();   // C2537
extern "C" void func2();   // OK
```