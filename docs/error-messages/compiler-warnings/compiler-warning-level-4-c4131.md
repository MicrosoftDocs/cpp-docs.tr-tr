---
title: "Derleyici Uyarısı (düzey 4) C4131 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4131
dev_langs: C++
helpviewer_keywords: C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 48e7ed1c5570e8bfa9d571cde649e618f51bcc2a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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