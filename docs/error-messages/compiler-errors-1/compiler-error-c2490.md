---
title: "Derleyici Hatası C2490 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2490
dev_langs:
- C++
helpviewer_keywords:
- C2490
ms.assetid: 9de6bddd-b2e2-4ce6-b33b-201a8c2c8c54
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d23f61e8e720e1d59ae258132e368505c44bbb13
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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