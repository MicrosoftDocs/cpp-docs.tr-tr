---
title: "Derleyici Hatası C2400 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2400
dev_langs: C++
helpviewer_keywords: C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 67c78a5b505c6891f8a15ca5d3e73a0ed490697e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2400"></a>Derleyici Hatası C2400
Satır içi derleyici sözdizimi hatası 'context'; 'belirteci' bulundu  
  
 Belirtecin Belirtilen adda bir sözdizimi hatası neden oldu.  
  
 Aşağıdaki örnek C2400 oluşturur:  
  
```  
// C2400.cpp  
// processor: x86  
int main() {  
   __asm {  
      heh ax,bx;   // C2400, heh is not a valid x86 instruction  
      mov ax,bx;   // OK  
   }  
}  
```