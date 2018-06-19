---
title: Derleyici Hatası C2571 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 96dea582cf5d1211d57eac94a7f70458a51542ae
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33230780"
---
# <a name="compiler-error-c2571"></a>Derleyici Hatası C2571
'function': sanal işlev Birliği 'union' olamaz  
  
 Sanal işlevle UNION bildirildi. Bir sanal işleve yalnızca bir sınıf veya yapı bildirebilirsiniz.  Olası çözümler:  
  
1.  UNION, bir sınıf veya yapı değiştirin.  
  
2.  İşlev olmayan olun.  
  
 Aşağıdaki örnek C2571 oluşturur:  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```