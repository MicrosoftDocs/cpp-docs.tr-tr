---
title: Derleyici Hatası C2793 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2793
dev_langs:
- C++
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ea378b2a875542eab431cf9cc30217f50c971af6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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