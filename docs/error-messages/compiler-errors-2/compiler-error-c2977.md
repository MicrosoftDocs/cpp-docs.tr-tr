---
title: "Derleyici Hatası C2977 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2977
dev_langs: C++
helpviewer_keywords: C2977
ms.assetid: 3c4218e0-5d03-4a2b-b757-c507c35f3542
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee9827e6a7af3679ec41425523af578117f46ffb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2977"></a>Derleyici Hatası C2977
'tanımlayıcısı': çok fazla tür bağımsız değişkenleri  
  
 Bir genel ya da şablon çok fazla sayıda gerçek bağımsız değişkenlere sahiptir. Doğru parametrelerin sayısı bulmak için genel ya da şablon bildirimine bakın.  
  
 Aşağıdaki örnek C2977 oluşturur:  
  
```  
// C2977.cpp  
// compile with: /c  
template<class T, int i>   
class MyClass {};  
  
template MyClass< int , 1, 1 >;   // C2977  
template MyClass< int , 1 >;   // OK  
```  
  
 Ayrıca C2977 genel türler kullanma ortaya çıkabilir:  
  
```  
// C2977b.cpp  
// compile with: /clr  
// C2977 expected  
generic <class T, class U>   
void f(){}  
  
generic <class T>   
ref struct GC1 {};  
  
int main() {  
   // Delete the following 2 lines to resolve.  
   GC1<int, char> ^ pgc1;  
   f<int,int,int>();  
  
   // OK  
   GC1<int> ^ pgc1;  
   f<int, int>();  
}  
```