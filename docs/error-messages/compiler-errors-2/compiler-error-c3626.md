---
title: "Derleyici Hatası C3626 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3626
dev_langs: C++
helpviewer_keywords: C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9acd9c4e08c082d27fbc564031c515ca2a680d30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3626"></a>Derleyici Hatası C3626
'anahtar sözcüğü': '__event' anahtar sözcüğü yalnızca kullanılabilir COM arabirimleri, üye işlevleri ve temsilciler işaretçileridir veri üyeleri  
  
 Bir anahtar sözcük yanlış kullanıldı.  
  
 Aşağıdaki örnek C3626 oluşturur:  
  
```  
// C3626.cpp  
// compile with: /c  
struct A {  
   __event int i;   // C3626  
// try the following line instead  
// __event int i();  
};  
```