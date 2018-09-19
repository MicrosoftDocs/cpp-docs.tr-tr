---
title: Derleyici Hatası C2313 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2313
dev_langs:
- C++
helpviewer_keywords:
- C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57e291788f261f0e62bd476b3027dfa809594ce3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024949"
---
# <a name="compiler-error-c2313"></a>Derleyici Hatası C2313

'type1': satır numarasında başvuru ('type2') tarafından yakalandı

Özel durum türü, iki işleyicileri vardır. İkinci yakalama ilk türü bir başvuru türüdür.

Aşağıdaki örnek, C2313 oluşturur:

```
// C2313.cpp
// compile with: /EHsc
#include <eh.h>
class C {};
int main() {
    try {
        throw "ooops!";
    }
    catch( C& ) {}
    catch( C ) {}   // C2313
}
```