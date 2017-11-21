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
ms.openlocfilehash: 46ff98cd80212268acdb8480edf01a3a47ce8708
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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