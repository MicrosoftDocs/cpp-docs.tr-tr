---
title: "Derleyici Hatası C2637 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2637
dev_langs: C++
helpviewer_keywords: C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f676205e2850e411ddb5e5b996114c00c65087f2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2637"></a>Derleyici Hatası C2637
'tanımlayıcısı': veri üye işaretçileri değiştirilemiyor  
  
 Bir veri üyesi için bir işaretçi bir arama kuralı sahip olamaz. Çözmek için çağırma kuralı kaldırmak veya üye işlevi için bir işaretçi bildirin.  
  
 Aşağıdaki örnek C2637 oluşturur:  
  
```  
// C2637.cpp  
// compile with: /c  
struct S {};  
int __stdcall S::*pms1;   // C2637  
  
// OK  
int S::*pms2;  
int (__stdcall S::*pms3)(...);  
```