---
title: "Derleyici Uyarısı (düzey 1) C4068 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4068
dev_langs: C++
helpviewer_keywords: C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4dd3b5f58027ab855f89fbb008c344436ca316ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4068"></a>Derleyici Uyarısı (düzey 1) C4068
Bilinmeyen pragması  
  
 Derleyici tanınmayan göz ardı [pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md). Mutlaka **pragma** kullanmakta olduğunuz derleyici tarafından izin verilir. Aşağıdaki örnek C4068 oluşturur:  
  
```  
// C4068.cpp  
// compile with: /W1  
#pragma NotAValidPragmaName   // C4068, use valid name to resolve  
int main()  
{  
}  
```