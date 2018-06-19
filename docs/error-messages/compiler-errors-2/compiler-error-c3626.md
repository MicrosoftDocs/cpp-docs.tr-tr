---
title: Derleyici Hatası C3626 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3626
dev_langs:
- C++
helpviewer_keywords:
- C3626
ms.assetid: 43926e2b-1ba9-4a43-9343-c58449cbb336
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ede2ec42b3afc581126d2591cba072817dcc8748
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33266174"
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