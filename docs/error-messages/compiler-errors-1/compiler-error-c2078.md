---
title: Derleyici Hatası C2078 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2078
dev_langs:
- C++
helpviewer_keywords:
- C2078
ms.assetid: 9bead850-4123-46cf-a634-5c77ba974b2b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab44fd94f34f80623b58dea01eee4e0143b6dbc4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2078"></a>Derleyici Hatası C2078
çok fazla başlatıcıları  
  
 Başlatıcılar sayısı başlatılması için nesne sayısını aşıyor.  
  
 İç küme ayraçları Başlatıcı listeden elided zaman derleyici başlatıcıları ve iç nesneleri için doğru atamasının türetme. Tam destek oluştur ayrıca belirsizliği ortadan kaldırır ve doğru atamasını sonuçlanır. Kısmi destek oluştur nesnelere başlatıcıları atamasında belirsizlik nedeniyle C2078 neden olabilir.  
  
 Aşağıdaki örnek C2078 oluşturur ve düzeltmek gösterilmektedir:  
  
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