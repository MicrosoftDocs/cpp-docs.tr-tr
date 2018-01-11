---
title: "Derleyici Hatası C3280 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3280
dev_langs: C++
helpviewer_keywords: C3280
ms.assetid: 86dc5bbc-8818-4786-a728-9334268d308b
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ca68d60e5a6413d4793402d9d9ed8dfe060272e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3280"></a>Derleyici Hatası C3280
'class': üye işlevi bir yönetilen türü yönetilmeyen işlev derlenemez  
  
 Sınıf üyesi işlevleri yönetilmeyen işlevleri derlenemez yönetilen.  
  
 Aşağıdaki örnek C3280 oluşturur:  
  
```  
// C3280_2.cpp  
// compile with: /clr  
ref struct A {  
   void func();  
};  
  
#pragma managed(push,off)  
  
void A::func()   // C3280  
{  
}  
  
#pragma managed(pop)  
```  
