---
title: "Derleyici Hatası C2249 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2249
dev_langs: C++
helpviewer_keywords: C2249
ms.assetid: bdd6697c-e04b-49b9-8e40-d9eb6d74f2b6
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 5878c28ed0b4fc2663c17021aa9e277ccaa8ad4e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2249"></a>Derleyici Hatası C2249
'member': erişim üyesine erişilebilir yol bildirilen sanal taban 'sınıfı'  
  
 `member` Ortak değil devralınan `virtual` temel sınıf veya yapı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2249 oluşturur.  
  
```  
// C2249.cpp  
class A {  
private:  
   void privFunc( void ) {};  
public:  
   void pubFunc( void ) {};  
};  
  
class B : virtual public A {} b;  
  
int main() {  
   b.privFunc();    // C2249, private member of A  
   b.pubFunc();    // OK  
}  
```  
  
## <a name="example"></a>Örnek  
 Başka bir akışa C++ Standart Kitaplığı'ndan bir akış atamak çalışırsanız C2249 da oluşabilir.  Aşağıdaki örnek C2249 oluşturur.  
  
```  
// C2249_2.cpp  
#include <iostream>  
using namespace std;  
int main() {  
   cout = cerr;   // C2249  
   #define cout cerr;   // OK  
}  
```