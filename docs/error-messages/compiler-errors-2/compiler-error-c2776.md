---
title: "Derleyici Hatası C2776 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2776
dev_langs:
- C++
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6a51ff76a635c1c55b0a12c28c8f1d93360dee6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2776"></a>Derleyici Hatası C2776
özellik yalnızca bir 'get' yöntemi belirtilebilir.  
  
 Yalnızca birini belirtebilirsiniz `get` işlevi [özelliği](../../cpp/property-cpp.md) genişletilmiş öznitelik. Bu hata oluştuğunda, birden çok `get` işlevleri belirtilir.  
  
 Aşağıdaki örnek C2776 oluşturur:  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```