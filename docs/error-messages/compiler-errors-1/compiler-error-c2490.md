---
title: "Derleyici Hatası C2490 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2490
dev_langs: C++
helpviewer_keywords: C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3c71f65364923af09e259cc722b5472f3603ba8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2490"></a>Derleyici Hatası C2490
'anahtar sözcüğü 'naked' özniteliği işlevinde izin verilmiyor'  
  
 Olarak tanımlanan bir işlev [naked](../../cpp/naked-cpp.md) yapılandırılmış özel durum işleme kullanamazsınız.  
  
 Aşağıdaki örnek C2490 oluşturur:  
  
```  
// C2490.cpp  
// processor: x86  
__declspec( naked ) int func() {  
   __try{}   // C2490, structured exception handling  
}  
```