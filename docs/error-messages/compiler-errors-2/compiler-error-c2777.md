---
title: "Derleyici Hatası C2777 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2777
dev_langs: C++
helpviewer_keywords: C2777
ms.assetid: 5fe158c0-2a65-488a-aca2-61d4a8b32d43
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 483e653fd93ca276fdb9a4d54e8feded4b8c8acc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2777"></a>Derleyici Hatası C2777
özellik yalnızca bir 'put' yöntemini belirtilebilir.  
  
 A [özelliği](../../cpp/property-cpp.md) declspec değiştiricisi sahip birden fazla `put` özelliği.  
  
 Aşağıdaki örnek C2777 oluşturur:  
  
```  
// C2777.cpp  
struct A {  
   __declspec(property(put=PutProp,put=PutPropToo))   // C2777  
   // try the following line instead  
   // __declspec(property(put=PutProp))  
      int prop;  
   int PutProp(void);  
   int PutPropToo(void);  
};  
```