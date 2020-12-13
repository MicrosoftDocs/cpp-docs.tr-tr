---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2078'
title: Derleyici hatası C2078
ms.date: 11/04/2016
f1_keywords:
- C2078
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
ms.openlocfilehash: 5ad78db99952c790a55dc2e1fddba0df227246d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151235"
---
# <a name="compiler-error-c2078"></a>Derleyici hatası C2078

çok fazla Başlatıcı

Başlatıcıların sayısı, başlatılacak nesne sayısını aşıyor.

Derleyici, başlatıcı listesinden iç küme ayraçları geri geldiğinde nesneler ve iç nesneler için doğru başlatıcıların atanmasını verebilir. Tüm brasel kullanımı, belirsizliği ortadan kaldırır ve doğru atamaya neden olur. Kısmi örgü, nesnelere başlatıcılar atamasında belirsizlik nedeniyle C2078 neden olabilir.

Aşağıdaki örnek C2078 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2078.cpp
// Compile by using: cl /c /W4 C2078.cpp
struct S {
   struct {
      int x, y;
   } z[2];
};

int main() {
   int d[2] = {1, 2, 3};   // C2078
   int e[2] = {1, 2};      // OK

   char a[] = {"a", "b"};  // C2078
   char *b[] = {"a", "b"}; // OK
   char c[] = {'a', 'b'};  // OK

   S s1{1, 2, 3, 4};       // OK
   S s2{{1, 2}, {3, 4}};   // C2078
   S s3{{1, 2, 3, 4}};     // OK
   S s4{{{1, 2}, {3, 4}}}; // OK
}
```
