---
title: Derleyici Hatası C2537 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2537
dev_langs:
- C++
helpviewer_keywords:
- C2537
ms.assetid: aee81d8e-300e-4a8b-b6c4-b3828398b34e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65db4fa66d147cc46c1a6013d07048892dfa0800
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46136029"
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