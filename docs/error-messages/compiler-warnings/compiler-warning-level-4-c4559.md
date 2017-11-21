---
title: "Derleyici Uyarısı (düzey 4) C4559 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4559
dev_langs: C++
helpviewer_keywords: C4559
ms.assetid: ed542f60-454d-45cb-85da-987ede61b1ab
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 046a3186554603d4a33b2eec78084dd76ec64e40
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4559"></a>Derleyici Uyarısı (düzey 4) C4559
'function': şemadaki; işlev kazançlar __declspec(modifier)  
  
 Bir işlev yeniden tanımlandı veya yeniden bildirilen ve ikinci tanımı veya bildirimi eklenen bir __**declspec** değiştiricisi (***değiştiricisi***). Bu uyarı, bilgi amaçlıdır. Bu uyarıyı çözmenin tanımları birini silin.  
  
 Aşağıdaki örnek C4559 oluşturur:  
  
```  
// C4559.cpp  
// compile with: /W4 /LD  
void f();  
__declspec(noalias) void f();   // C4559  
```