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
ms.workload: cplusplus
ms.openlocfilehash: ea37a3f210a2c379471b481fb0812b6c0630d32a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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