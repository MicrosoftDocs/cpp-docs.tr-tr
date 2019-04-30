---
title: Derleyici Hatası C2382
ms.date: 11/04/2016
f1_keywords:
- C2382
helpviewer_keywords:
- C2382
ms.assetid: 4d4436f9-d0d6-4bd0-b8ec-767b89adfb2f
ms.openlocfilehash: 4115a01f9e4dcab31a05bb3994109e97694121e6
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344868"
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