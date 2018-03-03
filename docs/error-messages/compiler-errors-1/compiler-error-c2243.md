---
title: "Derleyici Hatası C2243 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2243
dev_langs:
- C++
helpviewer_keywords:
- C2243
ms.assetid: b90065bb-d251-4ba9-8b4c-280ee13fa9c0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ae7349cce7e824af5621fba121e762aeccffa9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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