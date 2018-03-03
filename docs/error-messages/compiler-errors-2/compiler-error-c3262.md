---
title: "Derleyici Hatası C3262 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3262
dev_langs:
- C++
helpviewer_keywords:
- C3262
ms.assetid: 3e74b9aa-de3c-4492-9331-ee73012b958b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7dad91b2bc2d257d8c048a349d00ff8ec170fad8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3262"></a>Derleyici Hatası C3262
Geçersiz dizi dizin: '#' için belirtilen '#' dimension(s)-boyutlu 'dizi türü'  
  
Bir dizi alt yanlış. Dizin sayısı dizinin boyut sayısını eşleşmeyebilir.  
  
Aşağıdaki örnek C3262 oluşturur:  
  
```  
// C3262.cpp  
// compile with: /clr  
#using <mscorlib.dll>  
using namespace System;  
  
#define ARRAY_SIZE 2  
  
ref class MyClass {  
public:  
   int m_i;  
};  
  
// returns a multidimensional managed array of a reference type  
array<MyClass^, 2>^ Test0() {  
   int i, j;  
   array< MyClass^, 2 >^ local = new array< MyClass^, 2 >  
      (ARRAY_SIZE, ARRAY_SIZE);  
  
   for (i = 0 ; i < ARRAY_SIZE ; i++)  
      for (j = 0 ; j < ARRAY_SIZE ; j++) {  
         local[i][j] = new MyClass;   // C3262  
         // try the following line instead  
         // local[i,j] = new MyClass;     
         local[i,j] -> m_i = i;  
      }  
  
      return local;  
}  
  
int main() {     
   int i, j;  
  
   array< MyClass^, 2 >^ MyClass0;  
   MyClass0 = Test0();  
}  
```  
