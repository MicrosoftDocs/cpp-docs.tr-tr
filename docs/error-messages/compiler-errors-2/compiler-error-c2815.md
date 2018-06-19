---
title: Derleyici Hatası C2815 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2815
dev_langs:
- C++
helpviewer_keywords:
- C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 43eadfe636250c0acab9bcb2cd09323292f26a43
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33240824"
---
# <a name="compiler-error-c2815"></a>Derleyici Hatası C2815
'delete' işleci: ilk biçimsel parametresi olmalıdır ' void *', ancak 'param' kullanıldı  
  
 Herhangi bir kullanıcı tarafından tanımlanan [delete işleci](../../standard-library/new-operators.md#op_delete) işlevi türünde ilk biçimsel parametresi almalıdır `void *`.  
  
 Aşağıdaki örnek C2815 oluşturur:  
  
```  
// C2815.cpp  
// compile with: /c  
class CMyClass {  
public:  
   void mf1(int *a);  
   void operator delete(CMyClass *);   // C2815  
   void operator delete(void *);   
};  
```