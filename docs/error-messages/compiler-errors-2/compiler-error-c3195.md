---
title: "Derleyici Hatası C3195 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3195
dev_langs:
- C++
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 840aa93a7955c6eda2720da8457624e00fe97fca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3195"></a>Derleyici Hatası C3195
'işleci': ayrılmıştır ve ref sınıfı veya değer türünün bir üyesi olarak kullanılamaz. CLR veya WinRT işleçleri 'işleci' anahtar sözcüğünü kullanarak tanımlanmış olması gerekir  
  
Derleyici Yönetilen Uzantılar için C++ söz dizimini kullanarak bir işleç tanımı algıladı. C++ söz dizimini işleçler için kullanmanız gerekir.  
  
Aşağıdaki örnek C3195 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3195.cpp  
// compile with: /clr /LD  
#using <mscorlib.dll>  
value struct V {  
   static V op_Addition(V v, int i);   // C3195  
   static V operator +(V v, char c);   // OK for new C++ syntax   
};  
```