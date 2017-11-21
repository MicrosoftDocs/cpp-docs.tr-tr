---
title: "Derleyici Hatası C2506 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2506
dev_langs: C++
helpviewer_keywords: C2506
ms.assetid: cfed21cd-2404-46f2-985e-d0c2c3820830
caps.latest.revision: "5"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 200155978fe12a142519dd79e50cb409e9ea1e54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2506"></a>Derleyici Hatası C2506
'member': '__declspec(modifier)' bu simgeyi uygulanamaz  
  
 Yönetilen bir sınıfın statik üyeleri için işlem başına veya appdomain başına bildiremezsiniz.  
  
 Bkz: [appdomain](../../cpp/appdomain.md) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2506 oluşturur.  
  
```  
// C2506.cpp  
// compile with: /clr /c  
ref struct R {  
   __declspec(process) static int n;   // C2506  
   int o;   // OK  
};  
```