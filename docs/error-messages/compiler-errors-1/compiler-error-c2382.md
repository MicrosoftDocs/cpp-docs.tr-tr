---
title: Derleyici Hatası C2382 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2382
dev_langs:
- C++
helpviewer_keywords:
- C2382
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc54ef088cf756918abe385acd3e5bed6b856a8a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46085803"
---
# <a name="compiler-error-c2382"></a>Derleyici Hatası C2382

'function': yeniden tanımlama; farklı bir özel durum belirtimleri

Altında [/Za](../../build/reference/za-ze-disable-language-extensions.md), bu hata, bir işlev aşırı yüklemesi yalnızca girişiminde bulunuldu gösterir [özel durum belirtimi](../../cpp/exception-specifications-throw-cpp.md).

Aşağıdaki örnek, C2382 oluşturur:

```
// C2382.cpp
// compile with: /Za /c
void f1(void) throw(int) {}
void f1(void) throw(char) {}   // C2382
void f2(void) throw(char) {}   // OK
```