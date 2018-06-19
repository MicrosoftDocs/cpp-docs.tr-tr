---
title: Derleyici Hatası C2073 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2073
dev_langs:
- C++
helpviewer_keywords:
- C2073
ms.assetid: 57908234-be7a-4ce9-b0a7-8b1ad621865e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 27d68b36460eaf291647f097385f2645d4f384ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33168873"
---
# <a name="compiler-error-c2073"></a>Derleyici Hatası C2073
'tanımlayıcısı': kısmen başlatılmış dizinin öğeleri, bir varsayılan oluşturucusu olmalıdır  
  
 Çok az başlatıcıları için kullanıcı tanımlı türler veya sabit bir dizi belirtildi. Açık bir başlatıcı ve karşılık gelen kurucusu bir dizi üyesi için belirtilmezse, varsayılan bir oluşturucu sağlanmalıdır.  
  
 Aşağıdaki örnek C2073 oluşturur:  
  
```  
// C2073.cpp  
class A {  
public:  
   A( int );   // constructor for ints only  
};  
A a[3] = { A(1), A(2) };   // C2073, no default constructor  
```  
  
```  
// C2073b.cpp  
// compile with: /c  
class B {  
public:  
   B();   // default constructor declared  
   B( int );  
};  
B b[3] = { B(1), B(2) };   // OK  
```