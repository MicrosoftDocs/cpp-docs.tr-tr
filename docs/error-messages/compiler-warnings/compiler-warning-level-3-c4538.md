---
title: "Derleyici Uyarısı (Düzey 3) C4538 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4538
dev_langs: C++
helpviewer_keywords: C4538
ms.assetid: 747e3d51-b6d0-41c1-a726-7af3253b59d7
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d187b651211b323cdb466682778063bac0a7273
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4538"></a>Derleyici Uyarısı (Düzey 3) C4538
'type': const/volatile niteleyicileri bu türü desteklenmiyor  
  
 Niteleyici anahtar sözcüğü bir diziye yanlış uygulandı. Daha fazla bilgi için bkz: [dizi](../../windows/arrays-cpp-component-extensions.md).  
  
 Aşağıdaki örnek C4538 oluşturur:  
  
```  
// C4538.cpp  
// compile with: /clr /W3 /LD  
const array<int> ^f1();   // C4538  
array<const int> ^f2();   // OK  
```