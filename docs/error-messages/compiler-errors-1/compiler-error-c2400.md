---
title: Derleyici Hatası C2400 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2400
dev_langs:
- C++
helpviewer_keywords:
- C2400
ms.assetid: 1ba441ee-73f9-42a5-bfe9-fbeab93808eb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b6eb9ea25428138297cf85fe71e9c84b2364199
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33225482"
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