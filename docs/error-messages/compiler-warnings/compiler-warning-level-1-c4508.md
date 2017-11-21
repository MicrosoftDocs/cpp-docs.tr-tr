---
title: "Derleyici Uyarısı (düzey 1) C4508 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4508
dev_langs: C++
helpviewer_keywords: C4508
ms.assetid: c05f113b-b789-4df0-a4ef-78bce4767021
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6d29e821fe29720b065bd9f003e1349c80bbb5c5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4508"></a>Derleyici Uyarısı (düzey 1) C4508
'function': işlevi; bir değer döndürmesi gerekir 'void' dönüş türü varsayılır  
  
 İşlev dönüş türü belirtilmiş sahiptir. Bu durumda, C4430 de yangın ve derleyici (varsayılan değeri int'dır) C4430 tarafından bildirilen düzeltme uygular.  
  
 Bu uyarıyı çözmek için açıkça işlevlerin dönüş türü bildirmelidir.  
  
 Aşağıdaki örnek C4508 oluşturur:  
  
```  
// C4508.cpp  
// compile with: /W1 /c  
#pragma warning (disable : 4430)  
func() {}   // C4508  
void func2() {}   // OK  
```