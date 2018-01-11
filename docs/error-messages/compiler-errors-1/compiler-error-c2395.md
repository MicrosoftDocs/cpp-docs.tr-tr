---
title: "Derleyici Hatası C2395 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2395
dev_langs: C++
helpviewer_keywords: C2395
ms.assetid: 2d9e3b28-8c2c-4f41-a57f-61ef88fc2af0
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd12e17e04db071cc1d51e464b4f7a282695fedb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2395"></a>Derleyici Hatası C2395
' your_type::operator'op'': CLR veya WinRT işleci geçerli değil. En az bir parametre aşağıdaki türden olması gerekir: 'T', 'T %', 'T &', 'T ^', 'T ^ %', 'T ^ &', burada T 'your_type' =  
  
 Windows çalışma zamanı veya yönetilen türü bir işleç türü işleci döndürülen değerin türü ile aynı olan en az bir parametre içermiyor.  
  
 Aşağıdaki örnek C2395 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2395.cpp  
// compile with: /clr /c  
value struct V {  
   static V operator *(int i, char c);   // C2395  
  
   // OK  
   static V operator *(V v, char c);  
   // or  
   static V operator *(int i, V& rv);  
};  
```