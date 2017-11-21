---
title: "Derleyici Uyarısı (düzey 1) C4074 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4074
dev_langs: C++
helpviewer_keywords: C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ed6c744bd72198d5e8859a5a4527f303eb44e46d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4074"></a>Derleyici Uyarısı (düzey 1) C4074
ayrılmış derleyici başlatma alanına yerleştirir başlatıcıları  
  
 Tarafından belirtilen derleyici başlatma alan [#pragma init_seg](../../preprocessor/init-seg.md), Microsoft tarafından ayrılmış. Bu alandaki kod C çalışma zamanı kitaplığı başlatma önce yürütülen.  
  
 Aşağıdaki örnek C4074 oluşturur:  
  
```  
// C4074.cpp  
// compile with: /W1  
#pragma init_seg( compiler )   // C4074  
  
// try this line to resolve the warning  
// #pragma init_seg(user)  
  
int main() {  
}  
```