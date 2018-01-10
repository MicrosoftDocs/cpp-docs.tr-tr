---
title: "Derleyici Uyarısı (Düzey 3) C4521 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4521
dev_langs: C++
helpviewer_keywords: C4521
ms.assetid: 057d770c-ebcf-44cd-b943-1b1bb1ceaa8c
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cb06f8d2cdbc29f5c6f98dfaeb23eeffe1167ef8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4521"></a>Derleyici Uyarısı (Düzey 3) C4521
'class': belirtilen birden çok kopya oluşturucuları  
  
 Sınıfın tek bir türde birden çok kopya Oluşturucusu vardır. Bu uyarı, bilgi amaçlıdır; Oluşturucular programınıza çağrılabilir.  
  
 Kullanım [uyarı](../../preprocessor/warning.md) bu uyarıyı gizlemek için pragması.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4521 oluşturur.  
  
```  
// C4521.cpp  
// compile with: /EHsc /W3  
#include <iostream>  
  
using namespace std;  
class A {  
public:  
   A() { cout << "A's default constructor" << endl; }  
   A( A &o ) { cout << "A&" << endl; }  
   A( const A &co ) { cout << "const A&" << endl; }   // C4521  
};  
  
int main() {  
   A o1;         // Calls default constructor.  
   A o2( o1 );   // Calls A( A& ).  
   const A o3;   // Calls default constructor.  
   A o4( o3 );   // Calls A( const A& ).  
}  
```