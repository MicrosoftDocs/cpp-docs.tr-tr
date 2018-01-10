---
title: "Derleyici Hatası C2373 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2373
dev_langs: C++
helpviewer_keywords: C2373
ms.assetid: 7a08bf0b-852d-48be-ba75-70df9f4b5951
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16132b892c5a8dc3bc85e83683b0251246373ca4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2373"></a>Derleyici Hatası C2373
'tanımlayıcısı': şemadaki; farklı türde değiştiricileri  
  
 Tanımlayıcı ile farklı tür değiştiricisi zaten tanımlandı.  
  
 Aşağıdaki örnek C2373 oluşturur:  
  
```  
// C2373.h  
void __clrcall func( void );  
const int i = 20;  
```  
  
 Ve ardından:  
  
```  
// C2373.cpp  
// compile with: /c  
#include "C2373.h"  
extern void __cdecl func( void );   // C2373  
extern void __clrcall func( void );   // OK  
  
extern int i;   // C2373  
extern const int i;   // OK  
```