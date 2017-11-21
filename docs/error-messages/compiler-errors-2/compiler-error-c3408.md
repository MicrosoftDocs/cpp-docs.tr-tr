---
title: "Derleyici Hatası C3408 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3408
dev_langs: C++
helpviewer_keywords: C3408
ms.assetid: 1f5ea979-fb1e-4214-b310-6fd6ca8249b1
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 65861e03a6710cb328a111d0ade924909b9333b7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3408"></a>Derleyici Hatası C3408
'öznitelik': öznitelik şablonu tanımlarını izin verilmiyor  
  
 Öznitelikleri şablonu tanımlarını uygulanamaz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3408 oluşturur.  
  
```  
// C3408.cpp  
// compile with: /c  
template <class T> struct PTS {  
   enum {  
      IsPointer = 0,  
      IsPointerToDataMember = 0  
   };  
};  
  
template <class T>   
[coclass]   // C3408  
struct PTS<T*> {  
   enum {  
      IsPointer = 1,  
      IsPointerToDataMember = 0  
   };  
};  
  
template   
<class T, class U>   
struct PTS<T U::*> {  
   enum {  
      IsPointer = 1,  
      IsPointerToDataMember = 1  
   };  
};  
  
struct S{};  
  
extern "C" int printf(const char*,...);  
  
int main() {  
   S s, *pS;  
   int S::*ptm;  
  
   printf("PTS<S>::IsPointer == %d PTS<S>::IsPointerToDataMember == %d\n", PTS<S>::IsPointer, PTS<S>:: IsPointerToDataMember);  
   printf("PTS<S*>::IsPointer == %d PTS<S*>::IsPointerToDataMember == %d\n", PTS<S*>::IsPointer, PTS<S*>:: IsPointerToDataMember);  
   printf("PTS<int S::*>::IsPointer == %d PTS<int S::*>::IsPointerToDataMember == %d\n", PTS<int S::*>::IsPointer, PTS<int S::*>:: IsPointerToDataMember);  
}  
```