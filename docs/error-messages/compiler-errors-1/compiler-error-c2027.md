---
title: Derleyici Hatası C2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2027
dev_langs:
- C++
helpviewer_keywords:
- C2027
ms.assetid: a39150c0-ec04-45ec-934c-a838bfe76627
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be3c85d2ffbd3fffe4e1e6ce6dafc615f199c00a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167450"
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