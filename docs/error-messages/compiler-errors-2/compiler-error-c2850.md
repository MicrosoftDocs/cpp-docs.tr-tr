---
title: "Derleyici Hatası C2850 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2850
dev_langs: C++
helpviewer_keywords: C2850
ms.assetid: f3efe86c-4168-4e76-a133-3f8314c69f51
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22e6f77d843c0545dcb148a1adf74c050c5fbe3d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2850"></a>Derleyici Hatası C2850
'oluşturmak': yalnızca dosya kapsamda; izin verilen iç içe geçmiş bir yapı olmayabilir  
  
 Bazı pragmaları gibi yapıları yalnızca genel kapsamda yer alabilir.  
  
 Aşağıdaki örnek C2850 oluşturur:  
  
```  
// C2850.cpp  
// compile with: /c /Yc  
// try the following line instead  
// #pragma hdrstop  
namespace X {  
   #pragma hdrstop   // C2850  
};  
```