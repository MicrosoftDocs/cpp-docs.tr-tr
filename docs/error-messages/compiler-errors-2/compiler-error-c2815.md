---
title: "Derleyici Hatası C2815 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2815
dev_langs: C++
helpviewer_keywords: C2815
ms.assetid: d0256fd6-0721-4c99-b03c-52d96e77a613
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b6c438512dae910e0a42831e5f863f7b1766c097
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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