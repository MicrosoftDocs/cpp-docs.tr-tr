---
title: "Derleyici Hatası C2356 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2356
dev_langs: C++
helpviewer_keywords: C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a09e44133b6bea0f79df020b359719cf1a1754c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2356"></a>Derleyici Hatası C2356
başlatma segment çeviri birim sırasında değiştirmemeniz gerekir  
  
 Olası nedenler:  
  
-   `#pragma init_seg`Segment başlatma kodu tarafından öncesinde  
  
-   `#pragma init_seg`bir başkası tarafından öncesinde`#pragma init_seg`  
  
 Çözümlemek için modülün başlangıcına segment başlatma kodu taşıyın. Birden çok alana başlatılmalıdır, bunları modülleri ayırmak için taşıyın.  
  
 Aşağıdaki örnek C2356 oluşturur:  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```