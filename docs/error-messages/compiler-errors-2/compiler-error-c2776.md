---
title: Derleyici Hatası C2776 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2776
dev_langs:
- C++
helpviewer_keywords:
- C2776
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: afbf3c48e5445d101408c2539cc077071b639044
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33233774"
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