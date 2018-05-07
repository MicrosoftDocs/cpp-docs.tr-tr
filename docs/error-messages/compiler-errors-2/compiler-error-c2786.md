---
title: Derleyici Hatası C2786 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2786
dev_langs:
- C++
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 29fd0d8cf22be29757abd775e1bb844cb1a1bfbc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2786"></a>Derleyici Hatası C2786
'type': __uuidof için geçersiz işleç  
  
 [__Uuidof](../../cpp/uuidof-operator.md) işleci bağlı bir GUID veya türünde bir nesne gibi bir kullanıcı tarafından tanımlanan kullanıcı tarafından tanımlanan bir türü alır.  Olası nedenler:  
  
1.  Bağımsız değişken türü kullanıcı tanımlı değil.  
  
2.  `__uuidof` GUID bağımsız değişkende ayıklanamıyor.  
  
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