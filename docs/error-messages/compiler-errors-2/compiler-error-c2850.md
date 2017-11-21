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
ms.openlocfilehash: ac2619417a55d5125863eb7ffd7ef45e09a2d742
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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