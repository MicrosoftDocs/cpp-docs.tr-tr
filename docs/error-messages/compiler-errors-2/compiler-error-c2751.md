---
title: Derleyici Hatası C2751 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2751
dev_langs:
- C++
helpviewer_keywords:
- C2751
ms.assetid: 44a3abdf-8a87-4a09-b34b-532c220c310a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 26fe5354061c0839cd7569c018e84b0e4f2905e5
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2751"></a>Derleyici Hatası C2751
'parametresi': bir işlev parametresi adını tam  
  
 Bir tam ad işlevi parametre olarak kullanamazsınız.  
  
 Aşağıdaki örnek C2751 oluşturur:  
  
```  
// C2751.cpp  
namespace std {  
   template<typename T>  
   class list {};  
}  
  
#define list std::list  
void f(int &list){}   // C2751  
```