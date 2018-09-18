---
title: Derleyici Hatası C2614 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2614
dev_langs:
- C++
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d7c8674a733251750ea1b3ec75e1ee784ab2db1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045035"
---
# <a name="compiler-error-c2614"></a>Derleyici Hatası C2614

'class1': Geçersiz üye başlatma: 'class2' bir taban veya üye değil

Yalnızca üye veya temel sınıfları başlatma listesinden bir sınıf veya yapı için görünür.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2614 oluşturur.

```
// C2614.cpp
// compile with: /c
struct A {
   int i;
   A( int ia ) : B( i ) {};   // C2614 B is not a member of A
};

struct A2 {
   int B;
   int i;
   A2( int ia ) : B( i ) {};   // OK
};
```