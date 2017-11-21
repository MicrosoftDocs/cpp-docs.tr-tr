---
title: "Derleyici Hatası C2793 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2793
dev_langs: C++
helpviewer_keywords: C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af1f43489d8f12b5923cc46cc197e7b749338c83
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2793"></a>Derleyici Hatası C2793
'belirteci': beklenmeyen belirteç aşağıdaki '::', tanımlayıcısı veya beklenen'işleci ' anahtar sözcüğü  
  
 İzleyebileceğiniz yalnızca belirteçleri `__super::` tanımlayıcı ya da anahtar sözcük `operator`.  
  
 Aşağıdaki örnek C2793 oluşturur  
  
```  
// C2793.cpp  
struct B {  
   void mf();  
};  
  
struct D : B {  
   void mf() {  
      __super::(); // C2793  
   }  
};  
```