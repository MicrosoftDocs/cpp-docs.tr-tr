---
title: "Derleyici Hatası C2762 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2762
dev_langs: C++
helpviewer_keywords: C2762
ms.assetid: 8b81a801-fd48-40a1-8bee-0748795b12e4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15e96c7df9d407bcb3b0b5686b83c5e8c42c33fa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2762"></a>Derleyici Hatası C2762
'class': 'bağımsız değişkeni' için bir şablon bağımsız değişken olarak geçersiz bir ifade  
  
 Kullanırken [/Za](../../build/reference/za-ze-disable-language-extensions.md), derleyici gösteren bir işaretçi bir integral biçimine dönüştürmez.  
  
 Aşağıdaki örnek C2762 oluşturur:  
  
```  
// C2762.cpp  
// compile with: /Za  
template<typename T, T *pT>  
class X2 {};  
  
void f2() {  
   X2<int, 0> x21;   // C2762  
   // try the following line instead  
   // X2<int, static_cast<int *>(0)> x22;  
}  
```