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
ms.openlocfilehash: 6c774ad6f3a4f388f9428ead64e9d0a1fbc5882a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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