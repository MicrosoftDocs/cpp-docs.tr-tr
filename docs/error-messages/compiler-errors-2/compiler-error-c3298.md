---
title: "Derleyici Hatası C3298 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3298
dev_langs: C++
helpviewer_keywords: C3298
ms.assetid: 458c2680-95bb-4d5e-895f-ce4115844193
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a21b2d28120cb5e1c936b632d67ff28bb6568210
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3298"></a>Derleyici Hatası C3298
'constraint_1': 'constraint_2' ref kısıtlaması var ve 'constraint_1' değer kısıtlaması olduğundan 'constraint_2' kısıtlama olarak kullanılamaz  
  
 Kısıtlaması için birbirini dışlayan özellikleri belirtemezsiniz. Örneğin, bir genel tür parametresi için bir değer türünü ve bir başvuru türü kısıtlaması olamaz.  
  
 Daha fazla bilgi için bkz: [genel tür parametrelerindeki kısıtlamalar (C + +/ CLI)](../../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3298 oluşturur.  
  
```  
// C3298.cpp  
// compile with: /clr /c   
generic<class T, class U>  
where T : ref class  
where U : T, value class   // C3298  
public ref struct R {};  
```