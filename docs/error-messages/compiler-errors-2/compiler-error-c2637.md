---
title: Derleyici Hatası C2637 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2637
dev_langs:
- C++
helpviewer_keywords:
- C2637
ms.assetid: 58d94447-eb96-4d8f-a690-dd78d322462e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f4cc17927f3d0c161192ece8509599b48e4a5d16
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231554"
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