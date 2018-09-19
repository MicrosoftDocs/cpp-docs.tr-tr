---
title: Derleyici Uyarısı (düzey 1) C4286 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4286
dev_langs:
- C++
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1a796ee1956de0795f677afec90dd2a65bb3d1d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099531"
---
# <a name="compiler-warning-level-1-c4286"></a>Derleyici Uyarısı (düzey 1) C4286

'type1': satır numarası üzerinde taban sınıf ('type2') tarafından yakalandı

Belirtilen özel durum türü, bir önceki işleyici tarafından işlenir. İkinci yakalama türü ilk türünden türetilir. Özel durumlar bir temel sınıf için türetilmiş bir sınıf için özel durumlar yakalayın.

## <a name="example"></a>Örnek

```
//C4286.cpp
// compile with: /W1
#include <eh.h>
class C {};
class D : public  C {};
int main()
{
    try
    {
        throw "ooops!";
    }
    catch( C ) {}
    catch( D ) {}  // warning C4286, D is derived from C
}
```