---
title: "Derleyici Hatası C2640 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2640
dev_langs: C++
helpviewer_keywords: C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1e9018badacf3f9265e798f736abb6c975b4b994
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2640"></a>Derleyici Hatası C2640
'tanımlayıcısı': değiştiricisi geçersiz başvuru üzerinde __based  
  
 `__based` Değiştiricisi yalnızca işaretçileri üzerinde kullanılabilir.  
  
 Aşağıdaki örnek C2640 oluşturur:  
  
```  
// C2640.cpp  
void f(int i) {  
    void *vp;  
    int _based(vp) &vr = I;  // C2640  
}  
```