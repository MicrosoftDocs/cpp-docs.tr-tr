---
title: Derleyici Hatası C2078
ms.date: 11/04/2016
f1_keywords:
- C2078
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
ms.openlocfilehash: a800a6efa6e02f323b4b6597f1aa983f13674e83
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182814"
---
# <a name="compiler-error-c2078"></a>Derleyici Hatası C2078

çok fazla başlatıcı

Başlatıcılar başlatılacak nesne sayısını aşıyor.

İç küme ayraçları Başlatıcı listeden elided, derleyici doğru nesneleri ve iç nesneleri için başlatıcılar atamasını çıkarabilir. Tam destek oluştur belirsizliği ortadan kaldırır ve doğru atamasını sonuçlanır. Kısmi destek oluştur nesneleri için başlatıcılar atamasını belirsizlik nedeniyle C2078 neden olabilir.

Aşağıdaki örnek, C2078 oluşturur ve bu sorunun nasıl gösterir:

```
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