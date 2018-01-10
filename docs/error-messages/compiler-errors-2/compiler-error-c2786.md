---
title: "Derleyici Hatası C2786 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2786
dev_langs: C++
helpviewer_keywords: C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f7165e131f3594349471b50cdc81926a9bcf9d2f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2786"></a>Derleyici Hatası C2786
'type': __uuidof için geçersiz işleç  
  
 [__Uuidof](../../cpp/uuidof-operator.md) işleci bağlı bir GUID veya türünde bir nesne gibi bir kullanıcı tarafından tanımlanan kullanıcı tarafından tanımlanan bir türü alır.  Olası nedenler:  
  
1.  Bağımsız değişken türü kullanıcı tanımlı değil.  
  
2.  `__uuidof`GUID bağımsız değişkende ayıklanamıyor.  
  
 Aşağıdaki örnek C2786 oluşturur:  
  
```  
// C2786.cpp  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
  
int main() {  
   __uuidof(int);   // C2786  
   __uuidof(int *);   // C2786  
   __uuidof(A **);   // C2786  
  
   // no error  
   __uuidof(A);  
   __uuidof(A *);  
   __uuidof(A &);  
   __uuidof(A[]);  
  
   int i;  
   int *pi;  
   A **ppa;  
  
   __uuidof(i);      // C2786  
   __uuidof(pi);     // C2786  
   __uuidof(ppa);    // C2786  
}  
```