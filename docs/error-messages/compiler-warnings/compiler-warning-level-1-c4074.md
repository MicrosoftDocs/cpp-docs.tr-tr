---
title: "Derleyici Uyarısı (düzey 1) C4074 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4074
dev_langs:
- C++
helpviewer_keywords:
- C4074
ms.assetid: cd510e66-c338-4a86-a4d7-bfa1df9b16c3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e398518881ae7fd3fbbba70535da97e75cf6a5b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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