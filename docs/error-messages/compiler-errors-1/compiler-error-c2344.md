---
title: Derleyici Hatası C2344 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2344
dev_langs:
- C++
helpviewer_keywords:
- C2344
ms.assetid: a84c7b37-c84e-4345-8691-c23abb2dc193
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8c560d1fcd250a83501579ec80768b4ba2de57f0
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46110229"
---
# <a name="compiler-error-c2344"></a>Derleyici Hatası C2344

align(#): hizalama ikinin üssü olmalıdır

Kullanırken [hizalama](../../cpp/align-cpp.md) anahtar sözcüğü, geçirdiğiniz değer ikinin kuvveti olması gerekir.

Örneğin, 3 ikinin kuvveti olmadığı için aşağıdaki kodu C2344 oluşturur:

```
// C2344.cpp
// compile with: /c
__declspec(align(3)) int a;   // C2344
__declspec(align(4)) int b;   // OK
```