---
title: Derleyici Uyarısı (düzey 4) C4131 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4131
dev_langs:
- C++
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6563d5faf3a9f050deb3cb7831c1a908739c8532
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-4-c4131"></a>Derleyici Uyarısı (düzey 4) C4131
'function': eski Tarz bildirimcisi kullanır  
  
 Belirtilen işlev bildirimi prototip biçiminde değil.  
  
 Eski stil işlev bildirimleri prototip biçimine dönüştürülen.  
  
 Aşağıdaki örnek, bir eski stil işlev bildirimi gösterir:  
  
```  
// C4131.c  
// compile with: /W4 /c  
void addrec( name, id ) // C4131 expected  
char *name;  
int id;  
{ }  
```  
  
 Aşağıdaki örnek, bir prototip form gösterir:  
  
```  
void addrec( char *name, int id )  
{ }  
```