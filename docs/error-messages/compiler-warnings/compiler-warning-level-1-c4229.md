---
title: "Derleyici Uyarısı (düzey 1) C4229 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4229
dev_langs: C++
helpviewer_keywords: C4229
ms.assetid: aadfc83b-1e5f-4229-bd0a-9c10a5d13182
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 02ae82e18223373a3ee82c07f43ea65f7a92ec76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4229"></a>Derleyici Uyarısı (düzey 1) C4229
kullanılan anachronism: değiştiricileri verileri yok sayılır  
  
 Bir Microsoft değiştirici gibi kullanılarak `__cdecl` üzerinde veri bildirimi eski bir uygulamadır.  
  
## <a name="example"></a>Örnek  
  
```  
// C4229.cpp  
// compile with: /W1 /LD  
int __cdecl counter;   // C4229 cdecl ignored  
```