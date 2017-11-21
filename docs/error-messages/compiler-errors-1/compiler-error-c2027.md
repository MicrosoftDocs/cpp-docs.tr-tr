---
title: "Derleyici Hatası C2027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2027
dev_langs: C++
helpviewer_keywords: C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2a2fec9194858127ca08ecc0a891a81a91de48fa
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2027"></a>Derleyici Hatası C2027
Tanımsız türü 'type' kullanın  
  
 Tanımlanan kadar bir türü kullanılamaz. Hatayı gidermek için türü başvuran önce tam olarak tanımlanmış emin olun.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2027 oluşturur.  
  
```  
// C2027.cpp  
class C;  
class D {  
public:  
   void func() {  
   }  
};  
  
int main() {  
   C *pC;  
   pC->func();   // C2027  
  
   D *pD;  
   pD->func();  
}  
```  
  
## <a name="example"></a>Örnek  
 Bildirilen ancak tanımsız türü için bir işaretçi bildirmek mümkündür.  Ancak Visual C++ tanımsız türüne bir başvuru izin vermiyor.  
  
 Aşağıdaki örnek C2027 oluşturur.  
  
```  
// C2027_b.cpp  
class A;  
A& CreateA();  
  
class B;  
B* CreateB();  
  
int main() {  
   CreateA();   // C2027  
   CreateB();   // OK  
}  
```