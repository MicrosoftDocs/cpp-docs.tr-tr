---
title: Derleyici Hatası C2243 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 16bc95540488b0723869c735b7fc80b15f6e763b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2243"></a>Derleyici Hatası C2243
'type1' öğesinden 'dönüştürme türü' dönüştürme 'type2' var, ancak erişilemiyor  
  
 Erişim Koruması (`protected` veya `private`) bir işaretçi bir dönüştürme türetilmiş bir sınıf için temel sınıf için bir işaretçi engelledi.  
  
 Aşağıdaki örnek C2243 oluşturur:  
  
```  
// C2243.cpp  
// compile with: /c  
class B {};  
class D : private B {};  
class E : public B {};  
  
D d;  
B *p = &d;   // C2243  
  
E e;  
B *p2 = &e;  
```  
  
 Temel sınıflar ile `protected` veya `private` erişim türetilmiş sınıf istemciler için erişilebilir değil. Bu düzeyde bir erişim denetimi, temel sınıf istemcilere görünmez olması gereken bir uygulama ayrıntılarını olduğunu belirtmek için kullanılır. Türetilen sınıfın temel sınıfı için bir işaretçi bir türetilmiş sınıf işaretçi örtük dönüştürme erişimi için istemcileri istiyorsanız, ortak türetme kullanın.