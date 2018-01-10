---
title: "Derleyici Hatası C2458 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2458
dev_langs: C++
helpviewer_keywords: C2458
ms.assetid: ed21901f-1067-42f5-b275-19b480decf5c
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ded0e3c022a1feadbe03f635b718e819ec13c6bb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2458"></a>Derleyici Hatası C2458
'tanımlayıcısı': tanımındaki yeniden tanımlama  
  
 Sınıfı, yapısı, UNION veya numaralandırma kendi bildiriminde tanımlandı.  
  
 Aşağıdaki örnek C2458 oluşturur:  
  
```  
// C2458.cpp  
class C {  
   enum i { C };   // C2458  
};  
```