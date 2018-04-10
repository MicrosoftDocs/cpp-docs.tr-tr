---
title: Derleyici Hatası C3126 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C3126
dev_langs:
- C++
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5735de9365c5e05366f17a45e647563916009988
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3126"></a>Derleyici Hatası C3126
Yönetilen türü 'type' içinde ' union' UNION tanımlanamıyor  
  
 UNION içinde yönetilen tür tanımlanamaz.  
  
 Aşağıdaki örnek C3126 oluşturur:  
  
```  
// C3126_2.cpp  
// compile with: /clr /c  
ref class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```  
