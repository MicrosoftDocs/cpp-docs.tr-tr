---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2614'
title: Derleyici hatası C2614
ms.date: 11/04/2016
f1_keywords:
- C2614
helpviewer_keywords:
- C2614
ms.assetid: a550c1d5-8718-4e17-a888-b2619e00fe11
ms.openlocfilehash: 5bc0958b406c11299aee9b0d88c4b7b7401370ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338652"
---
# <a name="compiler-error-c2614"></a>Derleyici hatası C2614

' Class1 ': geçersiz üye başlatma: ' Class2 ' bir taban veya üye değil

Bir sınıf veya yapı için başlatma listesinde yalnızca üye veya temel sınıflar görünebilir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2614 oluşturur.

```cpp
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
