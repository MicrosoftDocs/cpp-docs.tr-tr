---
title: "Derleyici Hatası C2893 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2893
dev_langs: C++
helpviewer_keywords: C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6ad558968720a13b95fecc6860df5826b47874aa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2893"></a>Derleyici Hatası C2893
İşlev Şablonu 'şablon adı' özelleştirmek üzere başarısız oldu  
  
 İşlev şablonu özelleştirmek üzere derleyici başarısız. Bu hatanın birçok nedeni olabilir.  
  
 Genel olarak, bir C2893 hatayı gidermek için işlevin imzayı gözden geçirin ve her tür örneği emin olmak için yoludur.  
  
## <a name="example"></a>Örnek  
 C2893 oluşur çünkü `f`'s şablon parametresi `T` olmasını anlaşılabilen `std::map<int,int>`, ancak `std::map<int,int>` hiçbir üyenin `data_type` (`T::data_type` ile oluşturulabilir değil `T = std::map<int,int>`.). Aşağıdaki örnek C2893 oluşturur.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```